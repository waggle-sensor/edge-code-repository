# Edge Code Repository (ECR)

#### Lead(s): [Seongha Park](mailto:seongha.park@anl.gov) (App Certification), [Wolfgang Gerlach](mailto:wolfgang@uchicago.edu)(ECR Software Infrastructure)

### Overview:
The ECR manages and hosts bundled and packaged components that can be deployed and run on a Waggle node. Components can be source code (e.g. a Python script), compiled binaries (e.g. GPU-optimized code) and trained models. Most ECR Bundles have three parts:  
  1) The code that runs at the edge, 
  2) the configuration and source data, such as a deep learning model for inference, and 
  3) the performance profile that describes the performance of the ECR bundle.
  
  The most simple bundle in the ECR might be a Python script that can be periodically run on the Edge Processor and returns a calculated value.  Complex bundles might include large GPU-optimized codes. All bundles in the repository include significant metadata -- how they were built, where they can run, version information, performance information, as well as the tool chain needed to rebuild the bundle.  It is the “App Store” for Sage. The ECR also handles provenance and DOI generation. ECR will be a public repository for waggle edge codes, some of which might be approved for scheduling on a particular remote deployment.
  
### Requirements:

Edge bundles go through several stages, from being initially tested on a Virtual Waggle to testing and performance data from running on a real physical Waggle. The ECR must not only keep metadata about the bundle, but also access permissions. Sometimes Edge models may need to be protected -- for example an ML model that identifies endangered species under active poaching threats.  Therefore, not all Edge bundles will be completely open source. Separately, the SES will maintain a permission database on where and when models can be run.

### Use Cases:
#### User pushes a new Edge Bundle into the ECR:
* Using CTSS, a user develops a new Edge model.
* The model is annotated with runtime requirements (PyTorch, OpenCV, etc.)
* The model and the source code and possibly the training data are archived, along with metadata.
* A unique identifier for the Edge Bundle is generated.
#### User tests an Edge Bundle, or it is run from the SES:
* User runs an Edge Bundle on a VW or Real Waggle or schedules it for execution via the SES
* Data on performance is automatically collected and pushed into the ECR

### Milestones:
* Publish design document, including metadata definitions and access controls
* Deploy ECR performance tools across all Sage nodes (see WES milestones)
* Release ECR V1.0 with documentation for users to build and deploy edge applications
