Serverless SGX + Javascript

Javascript main benefits: Offloading computations to client

=> Disadvantage: Client-Side input not trustworthy

	- always validated at Server
	- many resources are wasted
	- computations must be public

Non-Web: SGX Resource Measurement with S-FaaS

- Accuracy of compute time, memory and network usage measurements
- It is possible to measure with S-FAAS 
- [3] analyzed Duktape and Google Engine in SGX Enclave
  - may be further analyzed with duktape
- Running Javascript Engines in SGX creates small Overhead 
- Duktape more lightweighted than Google's SecureV8 with higher performance
- Duktape has higher Throughput for easier functions
- [5] modified Enclave Enviroment to PIE Environment
  - decreases latency, number of isntances, throughput and tome cost
  - here the plugin enclaves are created in advance, host enclaves for serverless functions are created on demand
  - 

Web-Apps:

	- Benefit in Latency regarding higher amount of computations
	- Benefit in Scalalbility as Server can handle more clients

Improvements?

	- Can Non-Web Javascript Engines achieve any benefit in Latency and/or scalability by being excecuted in an enclave?
	- 

Serverless Java:

- Java is not the perfect language for serverless
- This is because it is a compiled language and not an interpreted one
- There will be more Memory Allocations than in interpreted languages
- If costs are also dependtent of memory, costs will increase
- Java is not as performant as other languages
- Cold start: takes longer as java packages are mostly bigger than in interpreted languages
	- Allocation to the server with free resources
	- Downloading of your function
	- Starting container
	- Starting runtime environment (for example JVM)
- But:
	- Many libraries used in applications are Java-only libraries
	- Some areas only utilize Java Applications => Should all applications be rewritten? Example fininacial sector!
	- GraalVM can produce JavaBytecode that can be utilized as a function in a faas
		- Decreases memory usage and cold start time as not that much memory is allocated
	- 





Resources:

[1] TrustJS: https://www.sec.cs.tu-bs.de/pubs/2017b-eurosec.pdf

[2] SFAAS: https://dl.acm.org/doi/pdf/10.1145/3338466.3358916https://css.csail.mit.edu/6.858/2019/projects/ajaybr-zyteka.pdfSecure 

[3] Trust More, Serverless: https://dl.acm.org/doi/pdf/10.1145/3319647.3325825

[4] Remote Computation Using SGX: https://dl.gi.de/bitstream/handle/20.500.12116/16281/sicherheit2018-16.pdf?sequence=1&isAllowed=y

[5] Confidential Serverless Made Efficient with Plug-In Enclaves: https://ipads.se.sjtu.edu.cn/zh/publications/LiISCA21.pdf

[6] Serverless Java: https://www.future-processing.com/blog/serverless-with-java/

[7] Java & Graal VM: https://medium.com/criciumadev/serverless-native-java-functions-using-graalvm-and-fn-project-c9b10a4a4859

[7] Serverless in the Fog, a survey: https://link.springer.com/content/pdf/10.1007/s00607-021-00924-y.pdf

