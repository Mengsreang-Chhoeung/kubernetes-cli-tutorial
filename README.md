# ឯកសារ Kubernetes CLI ជាភាសាខ្មែរ

![kubernetes thumbnail](/_thumbnail_doc/kubernetes.jpg "Kubernetes Tutorial")

## តើ Kubernetes ជាអ្វី?

- **Kubernetes** ជា container orchestration engine ដែលមានលក្ខណះជា open source ហើយវាប្រើសម្រាប់ automating deployment, scaling, នឹង management នៃ containerized applications ។ វាត្រូវបានអភិវឌ្ឍន៍ដោយ **Google** ។

## តើមានតម្រូវការអ្វីខ្លះទើបអាចសិក្សា Kubernetes បាន?

- ដើម្បីអាចសិក្សា **Kubernetes** បានគឺយើងត្រូវមានចំណេះដឹងទាក់ទងនឹង Docker, Linux, YAML, នឹង Command Lines ជាមុនសិន។ ចំណាំ: អ្នកមិនចាំបាច់ចេះពួកវា(Docker, Linux, YAML, នឹង Command Lines) ច្បាស់អីណាស់ណានោះទេ គ្រាន់តែយល់ថាវាយកមកធ្វើអ្វីខ្លះទៅបានហើយ។

## តើធ្វើយ៉ាងមិចបានអាចប្រើប្រាស់ Kubernetes បាន?

ដើម្បីអាចប្រើប្រាស់ Kubernetes បាន យើងត្រូវទាញយក Tools សិនគឺ **kubectl**។

- **kubectl** គឺជា command-line tool ដែលអនុញ្ញាតឲ្យយើងអាច run commands ដើម្បីបញ្ជាទៅ Kubernetes clusters ។ យើងអាចប្រើ kubectl សម្រាប់ deploy applications, ពិនិត្យ និងគ្រប់គ្រង cluster resources, នឹងអាចមើល logs ។ សម្រាប់ព័ត៍មានបន្ថែម អាចចូលមើលនេះបាន [`kubectl` reference documentation](https://kubernetes.io/docs/reference/kubectl/)

- សម្រាប់ **kubectl** គឺយើងអាចទាញយកបាននៅគ្រប់ OS ដូចជា Linux, macOS និង Windows ដែលអាចទាញយកតាមលីងខាងក្រោម:
    - [Install kubectl on Linux](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/)
    - [Install kubectl on macOS](https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/)
    - [Install kubectl on Windows](https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/)

- ខាងក្រោមនេះគឺជា Tools មួយចំនួនទៀតដែលវាជាជំនួយក្នុងការ configuration kubernetes ឲ្យយើងស្រាប់ៗសម្រាប់ប្រ់ើប្រាស់ Kubernetes បន្ថែមដែលមានដូចជា:
    - **kind**: គឺអាចឲ្យយើងអាច run Kubernetes នៅលើកុំព្យូទ័ររបស់យើងផ្ទាល់ ហើយ tool មួយនេះ ដើម្បីអាចប្រើបានគឺទាមទារឲ្យយើងមានជាការទាញយកនិង configured នូវ [Docker](https://docs.docker.com/get-docker/) ជាមុនសិន។ សម្រាប់ព័ត័មានបន្ថែម [`kind` Quick Start](https://kind.sigs.k8s.io/docs/user/quick-start/) ។
    - **minikube**: ដូច **kind** ដែរ ហើយវា run a single-node Kubernetes cluster នៅលើកុំព្យូទ័ររបស់យើងផ្ទាល់(រួមបញ្ចូលជាមួយនឹង Windows, macOS, នឹង Linux)។ សម្រាប់ព័ត័មានបន្ថែម [`minikube` Get Started](https://minikube.sigs.k8s.io/docs/start/) ។
    - **kubeadm**: គឺអាចឲ្យយើងអាចបង្កើតនិងគ្រប់គ្រង Kubernetes clusters ។ វាអនុវត្តនូវសកម្មភាពដែលចាំបាច់ដើម្បីយកនូវ minimum viable, secure cluster up និង running in a user friendly way ។ សម្រាប់ព័ត័មានបន្ថែម [`kubeadm` Install Guide](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/) ។

## <u>Hello Minikube</u>:

នៅក្នុងចំណុចនេះគឺយើងមកស្គាល់ពី command បញ្ជាមួយចំនួនដើម្បី play around ជាមួយនឹង **Kubernetes**​ ដោយប្រើ **minikube** ។ តែមុនអាច play around ជាមួយនឹង **Kubernetes** ដោយប្រើ **minikube** បានគឺយើងត្រូវទាញយកនូវ [**minikube**](https://minikube.sigs.k8s.io/docs/start/) ជាមុនសិន។

ខាងក្រោមនេះគឺជាតម្រូវការមុននឹងអាចទាញយក **minikube** បាន:

![minikube prerequisite thumbnail](/_thumbnail_doc/minikube_prerequisite.jpeg "Minikube Prerequisite")

ខាងក្រោមនេះគឺជាទាញយក **minikube**:

![minikube installation thumbnail](/_thumbnail_doc/minikube_installation.jpeg "Minikube Installation")

ខាងក្រោមនេះគឺជាការ verify ថានៅក្នុងកុំព្យូទ័ររបស់យើងបានទាញយកនូវ **minikube** ហើយឬនៅ ហើយដើម្បី verify បានគឺចូល command line មួយណាក៏បាន តែក្នុងនេះគឺយើងប្រើ cmd របស់ Window ។ បន្ទាប់ពីបានបើក cmd រួចរាល់គឺសរសេរ command ដូចខាងក្រោមដែលមានប្រអប់ក្រហមព័ទ្ធជុំវិញ ហើយបើលទ្ធផលចេញមាន version នឹង commit ដូចក្នុងរូបគឺមានន័យកុំព្យូទ័ររបស់យើងគឺបានទាញយកនូវ **minikube** បានរួចរាល់។

![minikube version thumbnail](/_thumbnail_doc/minikube_version.jpeg "Minikube Version")