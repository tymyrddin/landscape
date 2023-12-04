# Supply chain compromise

App squatting and fake apps are listed by MITRE as [Mobile Technique ID T1474](https://attack.mitre.org/techniques/T1474/): 

_Adversaries may manipulate products or product delivery mechanisms prior to receipt by a final consumer for the purpose of data or system compromise. Supply chain compromise can take place at any stage of the supply chain._

* Detection involves [application vetting](https://attack.mitre.org/datasources/DS0041/) of API calls, network communication, permissions requests, and protected configuration.

## Static analysis notes

Static analysis can be done with various tools to decompile the binary, such as [jadx](https://testlab.tymyrddin.dev/docs/dfir/jadx), [radare2](https://testlab.tymyrddin.dev/docs/dis/r2), [rizin](https://testlab.tymyrddin.dev/docs/dis/rizin), and [jeb](https://testlab.tymyrddin.dev/docs/dis/jeb). 

Tools such as [droidlysis](https://testlab.tymyrddin.dev/docs/dfir/droidlysis) for automatic offline static analysis can also be used. A high level description of the process can be found [here](https://dfir.tymyrddin.dev/docs/notes/mobile-analysis), and is applied in [Android malware analysis (Pithus and jadx)](https://dfir.tymyrddin.dev/docs/thm/android.md) as example.
