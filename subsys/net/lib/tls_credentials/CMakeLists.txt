# SPDX-License-Identifier: Apache-2.0

zephyr_include_directories(.)

zephyr_sources_ifdef(CONFIG_TLS_CREDENTIALS_BACKEND_VOLATILE
  tls_credentials.c
  tls_credentials_digest_raw.c
)
zephyr_sources_ifdef(CONFIG_TLS_CREDENTIALS_BACKEND_PROTECTED_STORAGE
  tls_credentials_trusted.c
  tls_credentials_digest_raw.c
)
zephyr_sources_ifdef(CONFIG_TLS_CREDENTIALS_SHELL
  tls_credentials_shell.c
)
