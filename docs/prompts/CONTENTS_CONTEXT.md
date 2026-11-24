# 1. Investigación de repositorios GitHub

El proyecto que describes va bastante más allá de un framework de reconocimiento convencional. Se aproxima a una combinación de cuatro tipos de plataformas:

- **EASM — External Attack Surface Management:** inventario de infraestructura y superficie de ataque externa.
- **Corporate Intelligence:** estructura empresarial, adquisiciones, filiales, proveedores y evolución corporativa.
- **OSINT Automation Framework:** adquisición, normalización, enriquecimiento y correlación automatizada de información pública.
- **Knowledge Graph & Evidence Management:** representación de relaciones, resolución de entidades, gestión de evidencias y niveles de confianza.

La diferencia fundamental respecto a herramientas como Amass o SpiderFoot debe ser que **el núcleo del sistema no sea el dominio de Internet, sino la entidad corporativa y todas sus relaciones empresariales y tecnológicas a lo largo del tiempo**.

Esto permitirá investigar desde una organización hacia sus activos tecnológicos, pero también recorrer las relaciones en sentido inverso.

## 1.1. Repositorios que más se aproximan al proyecto completo

La valoración de encaje es orientativa y se refiere a la arquitectura y funcionalidades que describes, no a la calidad general del software ni a una auditoría completa de su código.

| Repositorio | Encaje | Principal aportación |
|---|---:|---|
| [Open-EASM](https://github.com/zarguell/open-easm) | 9/10 | EASM pasivo, interfaz visual, correlación y grafos |
| [Pius](https://github.com/praetorian-inc/pius) | 9/10 | Descubrimiento de infraestructura partiendo de entidades empresariales |
| [OSINT-MCP](https://github.com/gglessner/OSINT-MCP) | 8.5/10 | Inteligencia corporativa, adquisiciones y descubrimiento de activos |
| [OWASP Amass](https://github.com/owasp-amass/amass) | 8.5/10 | Modelo de activos, relaciones y descubrimiento de infraestructura |
| [BBOT](https://github.com/blacklanternsecurity/bbot) | 8/10 | Arquitectura modular, eventos y enriquecimiento recursivo |
| [IntelOwl](https://github.com/intelowlproject/IntelOwl) | 7.5/10 | Orquestación de herramientas y gestión de enriquecimientos |
| [IVRE](https://github.com/ivre/ivre) | 7.5/10 | Almacenamiento, normalización e investigación de observaciones de red |
| [Scylax](https://github.com/pixelotes/scylax) | 7/10 | Inventario tecnológico y generación de informes EASM |

### 1. Open-EASM — referencia visual y funcional

**Repositorio:** [zarguell/open-easm](https://github.com/zarguell/open-easm?utm_source=chatgpt.com)

Es uno de los proyectos más próximos a la parte visual y funcional de lo que buscas. Está concebido como una plataforma EASM pasiva y autohospedada, con descubrimiento automatizado, encadenamiento de investigaciones, reglas de correlación y visualización interactiva mediante grafos.

**Qué aprovechar:**

- Diseño de la interfaz de investigación.
- Representación de activos y relaciones.
- Motor declarativo de correlación basado en YAML.
- Gestión de fuentes de información.
- Concepto de descubrimiento progresivo.
- Autenticación y gestión de acceso.

**Qué no adoptar directamente:**

- Su modelo de datos completo sin evaluar si soporta inteligencia corporativa.
- Las reglas de detección como afirmaciones automáticas de vulnerabilidades.
- La ausencia de autenticación como configuración inicial.

### 2. Pius — referencia principal de inteligencia corporativa e infraestructura

**Repositorio:** [praetorian-inc/pius](https://github.com/praetorian-inc/pius?utm_source=chatgpt.com)

Especialmente interesante para tu proyecto porque combina fuentes de infraestructura con registros corporativos, entre ellos GLEIF, SEC EDGAR y Wikidata.

Incluye una arquitectura de plugins, ejecución concurrente, caché, puntuación de confianza y mecanismos de degradación controlada cuando fallan fuentes de información.

**Qué aprovechar:**

- Descubrimiento basado en entidades corporativas.
- Integración de registros empresariales y de Internet.
- Arquitectura de plugins.
- Estrategia de caché.
- Gestión de fallos parciales.
- Modelado de confianza.
- Integración de los cinco registros regionales de Internet.

**Qué no adoptar directamente:**

- El lenguaje Go como requisito para todo el proyecto.
- Su clasificación de fuentes sin verificar el comportamiento real de cada plugin.
- La identificación automática de infraestructura como propiedad confirmada.

### 3. OSINT-MCP — referencia para conectores de inteligencia empresarial

**Repositorio:** [gglessner/OSINT-MCP](https://github.com/gglessner/OSINT-MCP?utm_source=chatgpt.com)

Su descripción incluye investigación de historia corporativa, adquisiciones, filiales, dominios, infraestructura y numerosas fuentes públicas.

En tu caso resulta especialmente interesante utilizarlo como catálogo de integraciones y referencia para el diseño de adaptadores.

**Qué aprovechar:**

- Organización de los conectores por área de conocimiento.
- Integración de fuentes empresariales.
- Separación entre investigación corporativa e infraestructura.
- Clientes de fuentes públicas.
- Normalización de respuestas.

**Qué no adoptar:**

- MCP como dependencia obligatoria.
- La exposición de todas las herramientas directamente a un LLM.
- La incorporación automática de conectores sin clasificación y revisión previa de sus efectos de red.

### 4. OWASP Amass — referencia para el modelo de activos

**Repositorio:** [owasp-amass/amass](https://github.com/owasp-amass/amass?utm_source=chatgpt.com)

Uno de sus componentes más interesantes para este proyecto es el **Open Asset Model**, además de sus mecanismos de descubrimiento y almacenamiento de activos. [OWASP Foundation](https://owasp.org/projects/amass?utm_source=chatgpt.com)

**Qué aprovechar:**

- Modelo de activos tecnológicos.
- Relaciones entre infraestructura y servicios.
- Normalización de observaciones.
- Enumeración mediante fuentes públicas.
- Representación de dependencias tecnológicas.

**Qué no adoptar:**

- Los mecanismos activos de reconocimiento.
- La dependencia de su modelo como única representación de la realidad corporativa.

### 5. BBOT — referencia para arquitectura modular

**Repositorio:** [blacklanternsecurity/bbot](https://github.com/blacklanternsecurity/bbot?utm_source=chatgpt.com)

Su arquitectura orientada a módulos y eventos resulta especialmente útil para estudiar cómo desacoplar herramientas que producen y consumen diferentes tipos de datos.

**Qué aprovechar:**

- Contratos entre módulos.
- Eventos tipados.
- Configuración de capacidades.
- Gestión de dependencias.
- Separación entre productores y consumidores de información.
- Formatos de salida estructurados.

**Qué no adoptar:**

- Recursividad ilimitada.
- Ejecución automática de módulos activos.
- Expansión del alcance basada exclusivamente en coincidencias técnicas.

### 6. IntelOwl — referencia de orquestación

**Repositorio:** [intelowlproject/IntelOwl](https://github.com/intelowlproject/IntelOwl?utm_source=chatgpt.com)

Interesante como referencia de una plataforma que coordina diferentes analizadores y fuentes de enriquecimiento.

**Qué aprovechar:**

- Gestión del ciclo de vida de trabajos.
- Integración de herramientas heterogéneas.
- Gestión de configuraciones y credenciales de proveedores.
- Visualización del estado de los análisis.
- Aislamiento de errores entre módulos.

### 7. IVRE — referencia para inteligencia de red

**Repositorio:** [ivre/ivre](https://github.com/ivre/ivre?utm_source=chatgpt.com)

Permite estudiar cómo almacenar, consultar y relacionar observaciones de red, tanto históricas como procedentes de diferentes fuentes.

**Qué aprovechar:**

- Modelado de observaciones de red.
- Consultas sobre infraestructura.
- Separación entre observaciones pasivas y activas.
- Importación de datos estructurados.
- Gestión de información histórica.

No utilizaría su motor de reconocimiento activo como parte de este proyecto.

## 1.2. Repositorios especializados que incorporaría

Hay una familia de proyectos especialmente interesante que no procede directamente de la ciberseguridad: las herramientas de investigación periodística y financiera. Resuelven problemas de identificación empresarial, procesamiento documental y correlación de evidencias que los frameworks de pentesting suelen tratar de forma superficial.

| Repositorio | Área | Qué aprovechar |
|---|---|---|
| [FollowTheMoney](https://github.com/opensanctions/followthemoney) | Inteligencia empresarial | Ontología de empresas, propiedades y relaciones |
| [Nomenklatura](https://github.com/opensanctions/nomenklatura) | Entity Resolution | Deduplicación, comparación y linaje de datos |
| [ICIJ Datashare](https://github.com/ICIJ/datashare) | Inteligencia documental | Indexación, extracción de entidades y búsqueda documental |
| [ICIJ Extract](https://github.com/ICIJ/extract) | Procesamiento documental | Extracción paralelizada de documentos heterogéneos |
| [Apache Tika](https://github.com/apache/tika) | Procesamiento documental | Extracción de texto y metadatos |
| [jaimefgdev/boe](https://github.com/jaimefgdev/boe) | Inteligencia empresarial española | Cliente Python para BOE y BORME |
| [Bormeparser](https://github.com/PabloCastellano/bormeparser) | Inteligencia empresarial española | Procesamiento de documentos del registro mercantil |
| [py-sec-edgar](https://github.com/ryansmccoy/py-sec-edgar) | Inteligencia financiera | Procesamiento de publicaciones y registros de la SEC |
| [Subfinder](https://github.com/projectdiscovery/subfinder) | Dominios | Enumeración pasiva mediante múltiples fuentes |
| [Gitleaks](https://github.com/gitleaks/gitleaks) | Seguridad documental y código | Detección local y notificación redactada de secretos |
| [Syft](https://github.com/anchore/syft) | Supply Chain | Inventario de componentes de software |

FollowTheMoney y Nomenklatura son particularmente valiosos porque proporcionan modelos de entidades, mecanismos de resolución y trazabilidad que se utilizan en plataformas reales de investigación. Datashare, por su parte, proporciona procesamiento documental, extracción de entidades y búsqueda mediante una interfaz web y REST API. [GitHub](https://github.com/opensanctions/followthemoney?utm_source=chatgpt.com)

## 1.3. Referencias complementarias por área

Además de los proyectos anteriores, incorporaría estas herramientas como dependencias candidatas, sujetas a comprobar su versión, licencia y comportamiento antes de integrarlas.

| Área | Repositorios |
|---|---|
| Arquitectura OSINT | [SpiderFoot](https://github.com/smicallef/spiderfoot), [Recon-ng](https://github.com/lanmaster53/recon-ng) |
| URLs históricas | [gau](https://github.com/lc/gau), [waymore](https://github.com/xnl-h4ck3r/waymore) |
| Certificados | [Cert Spotter](https://github.com/SSLMate/certspotter) |
| Metadatos | [ExifTool](https://github.com/exiftool/exiftool) |
| Secretos en material autorizado | [TruffleHog](https://github.com/trufflesecurity/trufflehog) |
| Dependencias | [OSV-Scanner](https://github.com/google/osv-scanner), [Syft](https://github.com/anchore/syft) |
| Extracción de publicaciones | [Trafilatura](https://github.com/adbar/trafilatura), [Feedparser](https://github.com/kurtmckee/feedparser) |
| Entity Resolution | [Splink](https://github.com/moj-analytical-services/splink), [Dedupe](https://github.com/dedupeio/dedupe) |
| NLP y NER | [GLiNER](https://github.com/urchade/GLiNER), [spaCy](https://github.com/explosion/spaCy) |
| Machine Learning | [scikit-learn](https://github.com/scikit-learn/scikit-learn) |
| Seguimiento de experimentos ML | [MLflow](https://github.com/mlflow/mlflow) |
| Grafos | [NetworkX](https://github.com/networkx/networkx), [Neo4j](https://github.com/neo4j/neo4j) |
| Visualización de grafos | [Cytoscape.js](https://github.com/cytoscape/cytoscape.js), [Sigma.js](https://github.com/jacomyal/sigma.js) |
| Búsqueda documental | [OpenSearch](https://github.com/opensearch-project/OpenSearch) |
| Inteligencia de vulnerabilidades | [Vulnerability-Lookup](https://github.com/vulnerability-lookup/vulnerability-lookup) |

## 1.4. Qué arquitectura elegiría

No haría un fork completo de ninguno de los proyectos. Construiría un núcleo independiente y utilizaría los anteriores como referencias arquitectónicas o herramientas intercambiables.

| Componente | Referencia principal |
|---|---|
| Arquitectura del motor | BBOT |
| Descubrimiento empresarial | Pius |
| Modelo de activos tecnológicos | OWASP Amass |
| Modelo de entidades corporativas | FollowTheMoney |
| Correlación y Entity Resolution | Nomenklatura |
| Orquestación de trabajos | IntelOwl |
| Interfaz visual | Open-EASM |
| Gestión documental | ICIJ Datashare |
| Observaciones de infraestructura | IVRE |
| Inteligencia corporativa española | Bormeparser y BOE |
| Catálogo de conectores | OSINT-MCP |

Estas referencias cubren partes complementarias del problema. Los proyectos EASM encontrados no deben asumirse pasivos en todos sus módulos: Amass, BBOT e IVRE también contemplan capacidades activas, por lo que es necesario verificar cada integración de manera independiente. [GitHub](https://github.com/owasp-amass/amass?utm_source=chatgpt.com)

La ventaja competitiva del nuevo proyecto debería estar en cinco capacidades:

1. **Inteligencia corporativa y tecnológica unificada:** no separar las adquisiciones y filiales de sus activos tecnológicos.
2. **Grafo temporal:** representar qué relaciones existían en cada momento y cuáles siguen respaldadas por evidencia reciente.
3. **Resiliencia:** múltiples proveedores por capacidad, recuperación ante fallos y medición de su rendimiento.
4. **IA entrenable:** utilizar los resultados y las correcciones humanas para mejorar la clasificación, extracción y correlación.
5. **Trazabilidad completa:** poder explicar de dónde procede cualquier nodo, relación o conclusión.

---

# 2. Prompt maestro para el agente de desarrollo

El prompt en PROJECT_CONTENTS.md está diseñado para entregarse directamente a Claude Code, Codex, OpenCode u otro agente de desarrollo. Es autocontenido y establece contratos de finalización por fase, evitando que el agente considere terminado un módulo por el mero hecho de haber generado su código.

He incorporado también redundancia de herramientas, entrenamiento de modelos con los datos recopilados, observabilidad y control de costes como requisitos transversales.

---

# 3. Evaluación de la arquitectura propuesta

El prompt convierte las características iniciales en un proyecto considerablemente más estructurado.

| Característica | Propuesta inicial | Prompt final |
|---|---|---|
| Inteligencia corporativa | Sí | 12 módulos independientes |
| Integración de herramientas | Sí | SDK y contratos comunes |
| Redundancia | Parcial | Capability Registry y fallback |
| Gestión de fallos | Básica | Circuit breakers y recuperación |
| Comparación de herramientas | No desarrollada | Benchmarks y métricas |
| Machine Learning | No desarrollado | Entrenamiento, evaluación y registro |
| Grafo de relaciones | Sí | Temporal, reversible y trazable |
| Adquisiciones | Sí | Modelo jurídico y temporal |
| Procesamiento documental | Sí | Pipeline independiente |
| Confianza | Sí | Multidimensional |
| Visualización | General | Vistas especializadas |
| API | General | REST versionada y WebSockets |
| Reproducibilidad | Parcial | Fixtures, CI y comandos estándar |
| DoD | No definido | Universal, por módulo y por fase |
| Seguridad del sistema | Básica | Threat model y pruebas específicas |
| Licencias | No desarrollado | Evaluación obligatoria |
| Monitorización recurrente | Parcial | Trabajos persistentes y controlados |

## Mi recomendación para el desarrollo

Distinguiría tres hitos comerciales y técnicos:

| Versión | Fases | Resultado |
|---|---|---|
| **v0.1 — Technical PoC** | 0–2 | Núcleo modular e inteligencia corporativa inicial |
| **v0.5 — Intelligence Engine** | 3–5 | Procesamiento, inventarios y correlación |
| **v1.0 — Corporate OSINT MVP** | 6 | Plataforma visual utilizable |
| **v2.0 — Adaptive Intelligence** | 7–8 | Modelos entrenables, optimización y hardening |

El mayor riesgo técnico del proyecto no es integrar las herramientas OSINT. Es **diseñar incorrectamente el modelo de datos y la resolución de entidades**, provocando que todas las correlaciones posteriores acumulen errores.

Por eso priorizaría especialmente **FollowTheMoney, Nomenklatura, Pius y OWASP Amass** antes de comenzar a construir el núcleo.

Si el modelo de entidades, evidencias y relaciones está bien diseñado, añadir cincuenta conectores adicionales en el futuro debería ser una ampliación del sistema, no una reconstrucción de su arquitectura.