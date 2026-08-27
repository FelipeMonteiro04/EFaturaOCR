# E-Fatura OCR Scanner (Cabo Verde)

Aplicação móvel nativa Android concebida para efetuar a leitura, validação estrutural e gestão local de faturas eletrónicas e documentos fiscais emitidos no sistema e-Fatura da DNRE em Cabo Verde.

---

## Funcionalidades

- Leitura de QR Code em Tempo Real: Utilização da biblioteca CameraX e Google ML Kit para deteção rápida do código IUD (Identificador Único do Documento).
- Análise Automática do IUD (45 caracteres):
  - Código do País e Repositório
  - Data de Emissão (AAMMDD)
  - NIF do Emissor
  - Código Lógico de Emissão (LED)
  - Tipo de Documento (Fatura, Fatura-Recibo, Nota de Crédito, Nota de Débito)
  - Número do Documento
  - Código de Segurança e Dígito Verificador (DV)
- Validação Estrutural: Verificação imediata da integridade do documento fiscal.
- Armazenamento Local: Guardado de forma segura na base de dados SQLite local com Room Database.
- Histórico de Faturas: Listagem reativa com suporte a Coroutines e Flow.

---

## Tecnologias Utilizadas

- Linguagem: Kotlin
- Câmara: AndroidX CameraX (Preview e ImageAnalysis)
- Processamento de Imagem / OCR: Google ML Kit Barcode Scanning
- Persistência de Dados: Room Database (SQLite)
- Concorrência: Kotlin Coroutines & Flow
- Interface: ViewBinding, Material Design 3, RecyclerView

---

## Estrutura do IUD (e-Fatura Cabo Verde)

A aplicação descodifica a sequência de 45 caracteres do IUD com base na seguinte estrutura:

| Posição | Tamanho | Descrição |
| :--- | :--- | :--- |
| 01-02 | 2 | Código do País (CV) |
| 03-03 | 1 | Código do Repositório |
| 04-09 | 6 | Data de Emissão (AAMMDD) |
| 10-18 | 9 | NIF do Emissor |
| 19-22 | 4 | Código Lógico de Emissão (LED) |
| 23-24 | 2 | Código do Tipo de Documento |
| 25-33 | 9 | Número do Documento |
| 34-43 | 10 | Código Aleatório de Segurança |
| 44-44 | 1 | Dígito Verificador (DV) |

---

## Instalação e Download

O executável da aplicação (ficheiro APK) encontra-se disponível para transferência direta na secção de Releases do repositório:
- Ficheiro: EFaturaOCR-v1.0.apk (disponível em Releases)

---

## Autor

Felipe Miguel Vieira Monteiro
Estudante de Engenharia Informática e de Computadores - Universidade de Cabo Verde

---

## Licença

Este projeto está licenciado sob a Licença MIT.

----------------------------------------------------------------------------------------------------

# E-Fatura OCR Scanner (Cape Verde)

Native Android mobile application designed to scan, perform structural validation, and manage electronic invoices locally for the DNRE e-Fatura system in Cape Verde.

---

## Features

- Real-time QR Code Scanning: Powered by AndroidX CameraX and Google ML Kit for quick detection of the IUD code (Unique Document Identifier).
- Automatic IUD Parsing (45 characters):
  - Country and Repository Code
  - Issue Date (YYMMDD)
  - Issuer Tax Identification Number (NIF)
  - Logical Emission Code (LED)
  - Document Type (Invoice, Receipt-Invoice, Credit Note, Debit Note)
  - Document Number
  - Security Code and Verification Digit (DV)
- Structural Validation: Instant integrity check of the fiscal document.
- Local Persistence: Secure local storage using Room Database (SQLite).
- Invoice History: Reactive UI updates using Kotlin Coroutines and Flow.

---

## Tech Stack

- Language: Kotlin
- Camera API: AndroidX CameraX (Preview and ImageAnalysis)
- Image Processing: Google ML Kit Barcode Scanning
- Database: Room Database (SQLite)
- Concurrency: Kotlin Coroutines & Flow
- User Interface: ViewBinding, Material Design 3, RecyclerView

---

## IUD Code Structure (Cape Verde e-Fatura)

The application parses the 45-character IUD string according to the following layout:

| Position | Length | Description |
| :--- | :--- | :--- |
| 01-02 | 2 | Country Code (CV) |
| 03-03 | 1 | Repository Code |
| 04-09 | 6 | Issue Date (YYMMDD) |
| 10-18 | 9 | Issuer NIF |
| 19-22 | 4 | Logical Emission Code (LED) |
| 23-24 | 2 | Document Type Code |
| 25-33 | 9 | Document Number |
| 34-43 | 10 | Random Security Code |
| 44-44 | 1 | Verification Digit (DV) |

---

## Download and Installation

The pre-compiled Android application package (APK file) is available for direct download in the Releases section of this repository:
- File: EFaturaOCR-v1.0.apk (available under Releases)

---

## Author

Felipe Miguel Vieira Monteiro
Computer and Informatics Engineering Student - Universidade de Cabo Verde

---

## License

This project is licensed under the MIT License.