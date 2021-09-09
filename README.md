[![LICENSE](https://img.shields.io/pypi/l/version_control.svg?style=flat-square)](https://raw.githubusercontent.com/kuter/django-version-control/master/LICENSE)
[![wemake-python-styleguide](https://img.shields.io/badge/style-wemake-000000.svg?style=flat-square)](https://github.com/wemake-services/wemake-python-styleguide)
[![gitmoji](https://img.shields.io/badge/gitmoji-%20😜%20😍-FFDD67.svg?style=flat-square)](https://gitmoji.carloscuesta.me)

# Django Login.gov.pl


## Instalacja

1. Korzystając z Python Package Index:

```bash
$ pip install git+https://github.com/RafalGandecki/django-logingovpl
```

2. Dodaj `logingovpl` do `INSTALLED_APPS`:

```python
INSTALLED_APPS = [
    ...
    'logingovpl',
]
```

3. Uzupełnij `urls.py` projektu:

```python
urlpatterns = [
    ...
    path('logingovpl/', include('logingovpl.urls')),
]
```

3. Konfiguracja:

Scieżki do kluczy ECSA:

```python
LOGINGOVPL_ENC_KEY = "pki/MinisterstwoCyfryzacji_MinisterstwoCyfryzacji_enc_ec.key"
LOGINGOVPL_ENC_CERT = "pki/MinisterstwoCyfryzacji_MinisterstwoCyfryzacji_enc_ec.pem"
```

Adres dostawcy tożsamości (domyślnie adres symulatora):

```python
LOGINGOVPL_ARTIFACT_RESOLVE_URL = "https://symulator.login.gov.pl/login-services/idpArtifactResolutionService"
LOGINGOVPL_SSO_URL = "https://symulator.login.gov.pl/login/SingleSignOnService"
LOGINGOVPL_SLO_URL = "https://symulator.login.gov.pl/login-services/singleLogoutService"
```

Adres po stronie dostawcy usługi na który wysyłana jest asercja:

```python
LOGINGOVPL_ASSERTION_CONSUMER_URL = "http://kro-dev.kronika.gov.pl/idp"
```

Identyfikator dostawcy usługi:

```python
LOGINGOVPL_ISSUER = "MinisterstwoCyfryzacji"
```

