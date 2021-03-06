# Orientación

Este documento es un resumen de las cosas que le contamos a los nuevos Colaboradores en su sesión de orientación.

## Una semana antes de la sesión de orientación

* Si el nuevo Colaborador todavía no es un miembro de la organización GitHub de nodjs, confirme que están utilizando [dos factores de autenticación](https://help.github.com/articles/securing-your-account-with-two-factor-authentication-2fa/). No será posible agregarlos a la organización si no están utilizando dos factores de autenticación. Si no pueden recibir mensajes SMS desde GitHub, intente [utilizando una aplicación móvil TOTP](https://help.github.com/articles/configuring-two-factor-authentication-via-a-totp-mobile-app/).
* Anunciar la nominación aceptada en una reunión de TSC y en la lista de correo TSC.
* Sugerir al nuevo Colaborador instalar [`node-core-utils`][] y [configurar las credenciales](https://github.com/nodejs/node-core-utils#setting-up-credentials) para ello.

## Quince minutos antes de la sesión de orientación

* Antes de la sesión de orientación, agregar al nuevo Colaborador al [Equipo de Colaboradores](https://github.com/orgs/nodejs/teams/collaborators).
* Pregúnteles si quieren unirse a algún equipo de subsistema. Consulte [A quien CC en el sistema de seguimiento de incidentes](../COLLABORATOR_GUIDE.md#who-to-cc-in-the-issue-tracker).

## Sesión de orientación

* Esta sesión cubrirá: 
  * [configuración local](#local-setup)
  * [objetivos & valores del proyecto](#project-goals--values)
  * [gestionar el sistema de seguimiento de incidentes](#managing-the-issue-tracker)
  * [revisión de PRs](#reviewing-prs)
  * [aterrizar PRs](#landing-prs)

## Configuración local

* git:
  
  * Asegúrese de tener espacio en blanco=corregir: `git config --global --add
apply.whitespace fix`
  * Siempre continuar el PR desde su propia bifurcación de GitHub 
    * Las ramas en el repositorio `nodejs/node` solo son para las líneas de lanzamiento
  * Consulte [Actualizar Node.js desde Upstream](./onboarding-extras.md#updating-nodejs-from-upstream)
  * Crear una nueva rama para cada PR que envíe.
  * Afiliación: Considere hacer su afiliación en la organización GitHub de Node.js pública. Esto hace que sea más fácil identificar a los Colaboradores. Las instrucciones sobre cómo hacerlo están disponibles en [Publicar u ocultar la afiliación a la organización](https://help.github.com/articles/publicizing-or-hiding-organization-membership/).

* Notificaciones:
  
  * Utilice <https://github.com/notifications> o configure el correo electrónico
  * Vea que el repositorio principal inundará su bandeja de entrada (varios cientos de notificaciones en días hábiles típicos), así que prepárese

* `#node-dev` en [webchat.freenode.net](https://webchat.freenode.net/) es el mejor lugar para interactuar con el TSC / otros Colaboradores
  
  * Si hay alguna pregunta después de la sesión, ¡un buen lugar para preguntar es ahí!
  * La presencia no es obligatoria, pero, por favor, deje una nota allí si hace push a la fuerza hacia `master`

## Objetivos & valores del proyecto

* Los Colaboradores son los propietarios colectivos del proyecto
  
  * El proyecto tiene los objetivos de sus contribuyentes

* Hay algunos objetivos y valores de alto nivel
  
  * La empatía hacía los usuarios es importante (esto es en parte la razón por la que orientamos a las personas)
  * En general: ¡intente ser amable con las personas!
  * El mejor resultado es que las personas que vengan a nuestro sistema de seguimiento de incidentes sientan que pueden volver.

* Se espera que siga *y* responsabilice a los demás ante el [Código de Conducta](https://github.com/nodejs/admin/blob/master/CODE_OF_CONDUCT.md).

## Gestionar el sistema de seguimiento de incidentes

* Tiene (en su mayoría) rienda suelta; no dude en cerrar un issue si está seguro de que debería cerrarse
  
  * ¡Sea amable en cuanto al cierre de incidentes! Deje que las personas sepan por qué, y que incidentes y PRs pueden ser reabiertos si es necesario

* [**Ver "Etiquetas"**](./onboarding-extras.md#labels)
  
  * Hay [un bot](https://github.com/nodejs-github-bot/github-bot) que aplica etiquetas de subsistema (por ejemplo, `doc`, `test`, `assert`, o `buffer`) para que sepamos qué partes del código base modifica el pull request. No es perfecto, por supuesto. Siéntase libre de aplicar etiquetas relevantes y eliminar etiquetas irrelevantes desde los pull requests y los incidentes.
  * Utilice la etiqueta `tsc-review` si un tema es controvertido o no llega a una conclusión después de un tiempo prolongado.
  * `semver-{minor,major}`: 
    * Si un cambio tiene la *posibilidad* remota de romper algo, utilice la etiqueta `semver-major`
    * Cuando agregue una etiqueta `semver-*`, añada un comentario explicando por qué lo agrega. ¡Hágalo de inmediato para que no se le olvide!
  * Por favor, agregue la etiqueta `author-ready` para PRs donde: 
    * el CI ha comenzado (no necesariamente terminado),
    * no existen comentarios pendientes para revisión y
    * al menor un colaborados aprobó el PR.

* Consulte [A quien CC en el sistema de seguimiento de incidentes](../COLLABORATOR_GUIDE.md#who-to-cc-in-the-issue-tracker).
  
  * Esto vendrá más naturalmente con el tiempo
  * Para muchos de los equipos enlistados, puede solicitar ser añadido si está interesado 
    * Algunos son WGs con algún proceso para agregar personas, otros solo están allí para notificaciones

* Cuando una discusión se calienta, puede requerir que otros Colaboradores la vigilen abriendo un issue en el repositorio privado [nodejs/moderation](https://github.com/nodejs/moderation).
  
  * Este es un repositorio al que todos los miembros de la organización GitHub de `nodejs` (no solo los Colaboradores del núcleo Node.js) tienen acceso. Sus contenidos no deben ser compartidos externamente.
  * Puede encontrar la política de moderación completa [aquí](https://github.com/nodejs/TSC/blob/master/Moderation-Policy.md).

## Revisión de PRs

* El objetivo principal es que el código base mejore.
* El secundario (pero no muy lejano) es que la persona que envía el código tenga éxito. Un pull request de un nuevo colaborador es un oportunidad para hacer crecer la comunidad.
* Revise un poco a la vez. No abrume a los nuevos colaboradores. 
  * Es tentador micro-optimizar. No sucumba a esa tentación. Cambiamos V8 a menudo. Las técnicas que proporcionan mejor rendimiento hoy, pueden ser innecesarias en el futuro.
* Tenga en cuenta: ¡Su opinión tiene mucho peso!
* Las nits (solicitudes para pequeños cambios que no son esenciales) están bien, pero intente evitar detener el pull request. 
  * Tenga en cuenta que son nits cuando comenta: `Nit: change foo() to bar().`
  * Si están deteniendo el pull request, corríjalos usted mismo en la fusión.
* En la medida de lo posible, los problemas deben ser identificados por las herramientas, en lugar de por los revisores humanos. Si está dejando comentarios sobre los problemas que podrían ser identificados por las herramientas pero no lo son, considere implementar las herramientas necesarias.
* Tiempo mínimo de espera para comentarios 
  * Hay un tiempo mínimo de espera que intentamos respetar para cambios no triviales, de modo que las personas que puedan tener aportes importantes en un proyecto tan distribuido sean capaces de responder.
  * Para cambios no triviales, deje abierto el pull request por al menos 48 horas (72 horas en fin de semana).
  * Si se abandona un pull request, verifique si les importaría que lo tomara (especialmente si solo faltan nits).

* Aprobar un cambio
  
  * Los colaboradores indican que han revisado y aprobado los cambios en un pull request utilizando la interfaz de aprobación de GitHub
  * A algunas personas les gusta comentar `LGTM` ("Me parece bien")
  * Tiene la autoridad para aprobar cualquier trabajo de otro colaborador.
  * No puede aprobar sus propios pull requests.
  * Cuando utilice explícitamente `Changes requested`, muestre empatía - los comentarios usualmente se abordarán incluso si no la utiliza. 
    * Si lo hace, es bueno que esté disponible luego para verificar si se han abordado sus comentarios
    * Si observa que los cambios requeridos han sido realizados, puede borrar la revisión de los `Changes requested` de otro colaborador.
    * Utilice `Changes requested` para indicar que está considerando alguno de sus comentarios para impedir que el PR sea aterrizado.

* Lo que pertenece en Node.js:
  
  * Las opiniones varían - ¡es bueno tener una extensa base de colaboradores por esa razón!
  * Si Node.js lo necesita (debido a razones históricas), entonces pertenece a Node.js. 
    * Es decir, el `url` está ahí debido a `http`, `freelist` está ahí debido a `http`, etc.
  * Cosas que no pueden ser hechas fuera del núcleo, o solo con un significativo dolor, como `async_hooks`.

* Prueba de Integración Continua (CI):
  
  * <https://ci.nodejs.org/> 
    * No se ejecuta automáticamente. Necesita iniciarlo manualmente.
  * Iniciar sesión en la CI está integrado con GitHub. ¡Intente iniciar sesión ahora!
  * Utilizará `node-test-pull-request` la mayor parte del tiempo. ¡Vaya allí ahora! 
    * Considere marcarlo: https://ci.nodejs.org/job/node-test-pull-request/
  * Para obtener el formulario para iniciar un trabajo, haga clic en `Construir con Parámetros`. (Si no lo ve, probablemente signifique que no ha iniciado sesión) ¡Haga clic ahora!
  * Para iniciar la prueba de CI desde esta pantalla, necesita rellenar dos elementos en el formulario: 
    * La caja `CERTIFY_SAFE` debe ser verificada. Al comprobarlo, está indicando que ha revisado el código que está a punto de probar y está seguro que no contiene ningún código malicioso. (¡No queremos que las personas secuestren nuestros hosts de CI para atacar otros hosts en internet, por ejemplo!)
    * La caja `PR_ID` debe completarse con el número que identifica al pull request que contiene el código que desea probar. Por ejemplo, si el URL para el pull request es `https://github.com/nodejs/node/issues/7006`, entonces coloque `7006` en el `PR_ID`.
    * Los elementos restantes en el formulario generalmente no cambian, con la excepción de `POST_STATUS_TO_PR`. Verifique si quiere que un indicador de estatus de CI sea insertado automáticamente dentro del PR.
  * Si necesita ayuda con algo relacionado con CI: 
    * Utilice #node-dev (IRC) para hablar con otros Colaboradores.
    * Utilice #node-build (IRC) para hablar con los miembros de Crear WG, los cuales mantienen la infraestructura de CI.
    * Utilice el [repo Crear WG](https://github.com/nodejs/build) para issues de archivos para los miembros de Crear WG que mantienen la infraestructura de CI.

## Aterrizar PRs

Consulte la Guía del Colaborador: [Aterrizar Pull Requests](https://github.com/nodejs/node/blob/master/COLLABORATOR_GUIDE.md#landing-pull-requests).

Tenga en cuenta que los commits en un PR que pertenecen a un cambio lógico deben ser aplastados. Rara vez es el caso de los ejercicios de orientación, por lo que esto debe ser señalado por separado durante la orientación.

<!-- TODO(joyeechueng): provide examples about "one logical change" -->

## Ejercicio: Haga un PR agregándose usted mismo al README

* Ejemplo: <https://github.com/nodejs/node/commit/ce986de829457c39257cd205067602e765768fb0> 
  * Para el mensaje de commit sin procesar: `git log ce986de829457c39257cd205067602e765768fb0
-1`
* Los colaboradores están ordenados alfabéticamente por el nombre de usuario de GitHub.
* Opcionalmente, incluya sus pronombres personales.
* Etiquete su pull request con la etiqueta de subsistema `doc`.
* Ejecute CI en el PR. A causa de que el PR no afecta ningún código, utilice la tarea de CI `node-test-pull-request-lite`. De manera alternativa, utilice la tarea usual de CI `node-test-pull-request` y cancélela después de que hayan pasado el linter y otra subtarea.
* Después de una o dos aprobaciones, aterrice el PR (PRs de este tipo no necesitan esperar 48/72 horas para ser recibidos). 
  * Asegúrese de añadir el `PR-URL: <full-pr-url>` y los metadatos correspondientes `Reviewed-By:`.
  * [`node-core-utils`][] automatiza la generación de metadatos y el proceso de aterrizaje. Consulte la documentación de [`git-node`][].
  * [`core-validate-commit`][] automatiza la validación de mensajes de commit. Esto se ejecutará durante `git node land --final` del comando [`git-node`][].

## Notas Finales

* No se preocupe por cometer errores: todo el mundo lo hace, hay mucho que interiorizar y eso lleva tiempo (¡y reconocemos eso!)
* Casi cualquier error que podría cometer puede ser arreglado o revertido.
* ¡Los Colaboradores existentes confían en usted y están agradecidos por su ayuda!
* Otros repositorios: 
  * <https://github.com/nodejs/TSC>
  * <https://github.com/nodejs/build>
  * <https://github.com/nodejs/nodejs.org>
  * <https://github.com/nodejs/readable-stream>
  * <https://github.com/nodejs/LTS>
  * <https://github.com/nodejs/citgm>
* La Fundación Node.js organiza cumbres periódicas para los colaboradores del proyecto Node.js, en el que tenemos discusiones cara-a-cara sobre nuestro trabajo en el proyecto. La Fundación tiene fondos para viajes para cubrir los gastos de los participantes incluyendo alojamiento, transporte, tarifas de visado, etc., si es necesario. Eche un vistazo al repositorio de [summit](https://github.com/nodejs/summit) para más detalles.