# HelmChart for Argo

이 리포지토리는 **Helm Chart를 통해 Kubernetes 애플리케이션을 배포하고, Argo CD를 활용하여 지속적 배포(CD)**를 구현하기 위한 프로젝트입니다. 해당 Helm Chart는 수동 배포와 GitOps 기반의 자동화를 모두 지원합니다.


## 주요 기능

- **Helm Chart 기반 수동 배포**  
  `helm install` 명령어를 사용하여 Kubernetes 클러스터에 애플리케이션을 직접 배포할 수 있습니다.

- **Argo CD 연동을 통한 자동화 배포**  
  Argo CD가 이 Helm Chart를 기반으로 애플리케이션을 모니터링하고, Git 리포지토리의 변경 사항을 감지하여 클러스터 상태를 자동으로 업데이트합니다.

- **효율적인 GitOps 지원**  
  GitOps 원칙에 따라 Kubernetes 리소스를 선언적으로 관리하며, Argo CD를 통해 배포 자동화 및 변경 이력을 추적할 수 있습니다.

- **템플릿 기반 Kubernetes 리소스 관리**  
  Deployment, Service, ConfigMap, Secret 등 Kubernetes 리소스를 템플릿화하여 다양한 환경에 맞춘 설정이 가능합니다.

- **다중 환경 및 유연한 설정 지원**  
  `values.yaml` 파일을 활용하여 개발, 스테이징, 프로덕션 등 여러 환경에 맞게 Helm Chart를 커스터마이징할 수 있습니다.

---

## 설치 방법

### 1. Helm 설치

Helm이 설치되어 있지 않다면 [Helm 공식 문서](https://helm.sh/docs/intro/install/)를 참조하여 설치하십시오.

```bash
# Helm 설치 확인
helm version
```

### 2. 리포지토리 클론

```bash
git clone https://github.com/SK-Rookies-Final3/HelmChart-for-Argo.git
cd HelmChart-for-Argo
```

### 3. Chart 설치

Helm을 사용하여 Chart를 설치합니다.

```bash
helm install <release-name> ./helm-charts
```

`<release-name>`에는 원하는 릴리스 이름을 입력합니다.

### 4. 설치 확인

설치 후 리소스가 정상적으로 배포되었는지 확인합니다.

```bash
kubectl get pods -n <namespace>
```

---

## 디렉토리 구조

```plaintext
HELMCHART-FOR-ARGO/
├── .github/                   # GitHub 워크플로 설정 파일
├── helm-charts/               # Helm Chart 디렉토리
│   ├── templates/             # 템플릿 파일
│   │   ├── backend-apigate.yaml
│   │   ├── backend-apigateway-service.yaml
│   │   ├── backend-brand-deployment.yaml
│   │   ├── backend-brand-service.yaml
│   │   ├── backend-users-deployment.yaml
│   │   ├── backend-users-service.yaml
│   │   ├── configmap.yaml
│   │   ├── front-deployment.yaml
│   │   ├── front-service.yaml
│   │   ├── ingress.yaml
│   │   ├── secret.yaml
│   │   └── shortpingoo-apigateway-rbac.yaml
│   ├── Chart.yaml             # Chart 메타데이터
│   └── values.yaml            # 기본 설정 파일
├── output/                    # 출력 관련 파일
├── iam-policy.json            # IAM 정책 파일
├── index.yaml                 # Helm 리포지토리 인덱스 파일
├── README.md                  # 프로젝트 설명
├── shortpingoo-0.1.0.tgz      # Helm 패키지
└── shortpingoo.json           # 기타 설정 파일
```

---

## 작성자

- **작성자 이름**: 황서정

---

## 기여하기

기여를 원하시면 PR(Pull Request)를 보내주시거나 이슈를 등록해주세요.

---

## 라이선스

이 프로젝트는 [MIT 라이선스](LICENSE)를 따릅니다.

---