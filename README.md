# RestAPI

API developed to use data made available on TJSP decisions and apply a simple CRUD API. Build for FIAP fase 3.


| Req    | Endpoint                               | Description                         | Success           | Error                      |
|--------|----------------------------------------|-------------------------------------|-------------------|----------------------------|
| POST   | juris/                                 | Create a new juris on the database  | Status:200        | Status: 500  - JSON        |
| GET    | juris/                                 | Read all juris from database        | Status:200 - JSON | Status: 500  - JSON        | 
| PUT    | juris/{id}                             | Update juris by given id            | Status:200 - JSON | Status: 500  - JSON        |
| DELETE | juris/{id}                             | Delete juris by given id            | Status:200 - JSON | Status: 500  - JSON        |
| GET    | juris/{id}                             | Read juris with given id            | Status:200 - JSON | Status: 500  - JSON        |


## Run Locally 
You need to build the database locally:
- run ```mysql -u root -p``` or similar to start MySQL
- [Database](https://github.com/Darklabel91/RestAPI/blob/master/Scripts/database)
- [Table](https://github.com/Darklabel91/RestAPI/blob/master/Scripts/table)
- [Insert](https://github.com/Darklabel91/RestAPI/blob/master/Scripts/Insert)

Don't forget to check and change it (if needed) the ```url``` ```username``` ```password``` on [dataSource](src/main/java/fiaprestapi/com/example/restapi/dataSource.java)

## Endpoint Examples
- GET juris/1 (error)
```json
{
    "timestamp": "2023-02-17T14:21:32.167+00:00",
    "status": 500,
    "error": "Internal Server Error",
    "trace": "java.lang.Exception: Juris not found!\n\tat fiaprestapi.com.example.restapi.controller.JurisprudenceController.findById(JurisprudenceController.java:40)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)\n\tat java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:77)\n\tat java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)\n\tat java.base/java.lang.reflect.Method.invoke(Method.java:568)\n\tat org.springframework.web.method.support.InvocableHandlerMethod.doInvoke(InvocableHandlerMethod.java:207)\n\tat org.springframework.web.method.support.InvocableHandlerMethod.invokeForRequest(InvocableHandlerMethod.java:152)\n\tat org.springframework.web.servlet.mvc.method.annotation.ServletInvocableHandlerMethod.invokeAndHandle(ServletInvocableHandlerMethod.java:117)\n\tat org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.invokeHandlerMethod(RequestMappingHandlerAdapter.java:884)\n\tat org.springframework.web.servlet.mvc.method.annotation.RequestMappingHandlerAdapter.handleInternal(RequestMappingHandlerAdapter.java:797)\n\tat org.springframework.web.servlet.mvc.method.AbstractHandlerMethodAdapter.handle(AbstractHandlerMethodAdapter.java:87)\n\tat org.springframework.web.servlet.DispatcherServlet.doDispatch(DispatcherServlet.java:1080)\n\tat org.springframework.web.servlet.DispatcherServlet.doService(DispatcherServlet.java:973)\n\tat org.springframework.web.servlet.FrameworkServlet.processRequest(FrameworkServlet.java:1011)\n\tat org.springframework.web.servlet.FrameworkServlet.doGet(FrameworkServlet.java:903)\n\tat jakarta.servlet.http.HttpServlet.service(HttpServlet.java:705)\n\tat org.springframework.web.servlet.FrameworkServlet.service(FrameworkServlet.java:885)\n\tat jakarta.servlet.http.HttpServlet.service(HttpServlet.java:814)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:223)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:158)\n\tat org.apache.tomcat.websocket.server.WsFilter.doFilter(WsFilter.java:53)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:185)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:158)\n\tat org.springframework.web.filter.RequestContextFilter.doFilterInternal(RequestContextFilter.java:100)\n\tat org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:116)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:185)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:158)\n\tat org.springframework.web.filter.FormContentFilter.doFilterInternal(FormContentFilter.java:93)\n\tat org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:116)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:185)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:158)\n\tat org.springframework.web.filter.CharacterEncodingFilter.doFilterInternal(CharacterEncodingFilter.java:201)\n\tat org.springframework.web.filter.OncePerRequestFilter.doFilter(OncePerRequestFilter.java:116)\n\tat org.apache.catalina.core.ApplicationFilterChain.internalDoFilter(ApplicationFilterChain.java:185)\n\tat org.apache.catalina.core.ApplicationFilterChain.doFilter(ApplicationFilterChain.java:158)\n\tat org.apache.catalina.core.StandardWrapperValve.invoke(StandardWrapperValve.java:177)\n\tat org.apache.catalina.core.StandardContextValve.invoke(StandardContextValve.java:97)\n\tat org.apache.catalina.authenticator.AuthenticatorBase.invoke(AuthenticatorBase.java:542)\n\tat org.apache.catalina.core.StandardHostValve.invoke(StandardHostValve.java:119)\n\tat org.apache.catalina.valves.ErrorReportValve.invoke(ErrorReportValve.java:92)\n\tat org.apache.catalina.core.StandardEngineValve.invoke(StandardEngineValve.java:78)\n\tat org.apache.catalina.connector.CoyoteAdapter.service(CoyoteAdapter.java:357)\n\tat org.apache.coyote.http11.Http11Processor.service(Http11Processor.java:400)\n\tat org.apache.coyote.AbstractProcessorLight.process(AbstractProcessorLight.java:65)\n\tat org.apache.coyote.AbstractProtocol$ConnectionHandler.process(AbstractProtocol.java:859)\n\tat org.apache.tomcat.util.net.NioEndpoint$SocketProcessor.doRun(NioEndpoint.java:1734)\n\tat org.apache.tomcat.util.net.SocketProcessorBase.run(SocketProcessorBase.java:52)\n\tat org.apache.tomcat.util.threads.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1191)\n\tat org.apache.tomcat.util.threads.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:659)\n\tat org.apache.tomcat.util.threads.TaskThread$WrappingRunnable.run(TaskThread.java:61)\n\tat java.base/java.lang.Thread.run(Thread.java:833)\n",
    "message": "Juris not found!",
    "path": "/juris/1"
}
```

- GET juris/2
```json
{
    "lawsuit_class": "Embargos de Declara????o C??vel / Desapropria????o Indireta",
    "lawsuit_judge": "Daniel Fillol",
    "lawsuit_city": "Porto Ferreira",
    "trial_date": "01-10-2021",
    "decision_short": "Recurso. A????o de Indeniza????o por Apossamento Administrativo (Desapropria????o Indireta) movida contra o DER, em fase de execu????o. D??bito atingido pela morat??ria constitucional do artigo 78 do Ato das Disposi????es Constitucionais Transit??rias. Senten??a que julgou extinta a execu????o (art. 924, inc. II, CPC). D??bito atingido pela morat??ria constitucional do artigo 78 do Ato das Disposi????es Constitucionais Transit??rias. Hip??tese em que deve prevalecer o quanto determinado no t??tulo sob execu????o. Inviabilidade, ademais, de aplica????o do artigo 5?? da Lei Federal n?? 11.960/09, declarado inconstitucional \"por arrastamento\" pelo STF. Ademais, se ?? aplic??vel o artigo 78 do ADCT ?? esp??cie, isto se d?? porque o pagamento, \"ipso facto\", n??o ocorreu no prazo contemplado na parte permanente da Constitui????o, de modo que devem ser computados juros morat??rios sobre as parcelas devidas. Ademais, o STF, na aprecia????o de medida cautelar nas ADIs 2356 e 2362, suspendeu a efic??cia do art. 2?? da EC 30/00. Inaplicabilidade ?? esp??cie da S??mula Vinculante n?? 17 do STF. N??o h??, ademais, na esp??cie, t??tulo judicial a amparar a pretendida execu????o contra os autores, ora exequentes. Princ??pios da economia e da celeridade processuais ininvoc??veis diante da regra do art. 783 do CPC. Eventual saldo credor em favor do executado-apelante dever?? ser apurado em a????o pr??pria. Recurso Extraordin??rio da Autarquia. Autos restitu??dos ?? C??mara pela Egr??gia Presid??ncia da Se????o de Direito P??blico, para os fins do artigo 1.040, II, do CPC. Mat??ria objeto de repercuss??o geral nos autos do Recurso Extraordin??rio n?? 590.751 (Tema n?? 132) e Recurso Extraodin??rio 1.169.289/SC (Tema 1.037). Hip??tese em que o Ac??rd??o recorrido n??o discrepou do entendimento exarado pelo Supremo Tribunal Federal. Restitui????o dos autos ?? Colenda Presid??ncia da Se????o de Direito P??blico deste Tribunal de Justi??a, por n??o se tratar de caso de poss??vel retrata????o nos termos e para os fins do artigo 1.040, inciso II, do CPC."
}
```

- GET juris/
```json
[
    {
        "lawsuit_class": "Embargos de Declara????o C??vel / Desapropria????o Indireta",
        "lawsuit_judge": "Daniel Fillol",
        "lawsuit_city": "Porto Ferreira",
        "trial_date": "01-10-2021",
        "decision_short": "Recurso. A????o de Indeniza????o por Apossamento Administrativo (Desapropria????o Indireta) movida contra o DER, em fase de execu????o. D??bito atingido pela morat??ria constitucional do artigo 78 do Ato das Disposi????es Constitucionais Transit??rias. Senten??a que julgou extinta a execu????o (art. 924, inc. II, CPC). D??bito atingido pela morat??ria constitucional do artigo 78 do Ato das Disposi????es Constitucionais Transit??rias. Hip??tese em que deve prevalecer o quanto determinado no t??tulo sob execu????o. Inviabilidade, ademais, de aplica????o do artigo 5?? da Lei Federal n?? 11.960/09, declarado inconstitucional \"por arrastamento\" pelo STF. Ademais, se ?? aplic??vel o artigo 78 do ADCT ?? esp??cie, isto se d?? porque o pagamento, \"ipso facto\", n??o ocorreu no prazo contemplado na parte permanente da Constitui????o, de modo que devem ser computados juros morat??rios sobre as parcelas devidas. Ademais, o STF, na aprecia????o de medida cautelar nas ADIs 2356 e 2362, suspendeu a efic??cia do art. 2?? da EC 30/00. Inaplicabilidade ?? esp??cie da S??mula Vinculante n?? 17 do STF. N??o h??, ademais, na esp??cie, t??tulo judicial a amparar a pretendida execu????o contra os autores, ora exequentes. Princ??pios da economia e da celeridade processuais ininvoc??veis diante da regra do art. 783 do CPC. Eventual saldo credor em favor do executado-apelante dever?? ser apurado em a????o pr??pria. Recurso Extraordin??rio da Autarquia. Autos restitu??dos ?? C??mara pela Egr??gia Presid??ncia da Se????o de Direito P??blico, para os fins do artigo 1.040, II, do CPC. Mat??ria objeto de repercuss??o geral nos autos do Recurso Extraordin??rio n?? 590.751 (Tema n?? 132) e Recurso Extraodin??rio 1.169.289/SC (Tema 1.037). Hip??tese em que o Ac??rd??o recorrido n??o discrepou do entendimento exarado pelo Supremo Tribunal Federal. Restitui????o dos autos ?? Colenda Presid??ncia da Se????o de Direito P??blico deste Tribunal de Justi??a, por n??o se tratar de caso de poss??vel retrata????o nos termos e para os fins do artigo 1.040, inciso II, do CPC."
    },
    {
        "lawsuit_class": " Apela????o Criminal / Desacato",
        "lawsuit_judge": " Grassi Neto",
        "lawsuit_city": " Brotas",
        "trial_date": "29-09-2021",
        "decision_short": " Resist??ncia e desacato - Conjunto probat??rio desfavor??vel ao r??u lastrado em depoimentos coerentes e harm??nicos das v??timas policiais ??? Sufici??ncia ?? aferi????o da realiza????o dos tipos penais, da autoria e do doloA jurisprud??ncia tem se inclinado no sentido de que, n??o havendo fundado motivo que recomende seja a palavra do policial considerada com reservas, suas declara????es dever??o revestir-se de presun????o de veracidade e de legitimidade, que ?? inerente aos atos administrativos em geral, tendo especial import??ncia, tanto para confirmar os fatos, quanto sua autoria e dolo, referentes a abordagem, da qual resultou pris??o do agente por resist??ncia e desacato, ao ?? opor-se ?? execu????o de ato legal, mediante viol??ncia ou amea??a a funcion??rio competente para execut??-lo ou a quem lhe esteja prestando aux??lio, bem como ao preferir express??o que visava a humilhar funcion??rio p??blico no exerc??cio de suas fun????es. "
    },
    {
        "lawsuit_class": " Apela????o C??vel / Desapropria????o Indireta",
        "lawsuit_judge": " Flora Maria Nesi Tossi Silva",
        "lawsuit_city": " Piracicaba",
        "trial_date": "24-09-2021",
        "decision_short": " EXPEDIENTE DA PRESID??NCIA DA SE????O DE DIREITO P??BLICO. DESAPROPRIA????O INDIRETA, movida em 1978, EM FASE DE EXECU????O. V. ac??rd??os (da fase de cumprimento de senten??a), proferidos em 07.11.2012 e 30.01.2013.Devolu????o dos autos ?? Turma Julgadora pela E. Presid??ncia da Se????o de Direito P??blico deste Tribunal de Justi??a para eventual adequa????o da fundamenta????o e/ou manuten????o da decis??o (art. 1.040, inciso II, do CPC/2015).Desnecessidade de adequa????o dos v. ac??rd??os proferidos por esta C. 13?? C??mara de Direito P??blico. Inaplicabilidade dos temas 810 do STF e 905 do STJ ao caso quanto aos juros, considerando que se trata de a????o de desapropria????o indireta, que apresenta regramento pr??prio sobre os juros.No tocante ?? corre????o monet??ria, observo que o t??tulo exequendo ?? oriundo de a????o ajuizada no ano de 1978, com fixa????o de corre????o monet??ria e juros de mora vigentes ??quela ??poca. Precat??rio pago em 08 parcelas, tendo sido o ??ltimo dep??sito realizado no ano de 2011. A aplica????o da Lei 11.960/09 a partir de sua vig??ncia dar-se-ia com desprezo das peculiaridades do caso concreto, revelando ofensa ?? coisa julgada e ao princ??pio da seguran??a e certeza das rela????es jur??dicas.V. AC??RD??OS RATIFICADOS, CONSIDERANDO A SITUA????O PECULIAR DO CASO CONCRETO.  "
    },
    {
        "lawsuit_class": " Embargos de Declara????o Criminal / Crimes contra a Flora",
        "lawsuit_judge": " Laerte Marrone",
        "lawsuit_city": " Avar??",
        "trial_date": "28-09-2021",
        "decision_short": " Embargos de declara????o. Alega????o de erro material, omiss??o e contradi????o. 1. Erro material configurado na parte inicial do voto: corre????o determinada. 2. Aus??ncia de contradi????o ou omiss??o no julgado. Irresigna????o que externa simples inconformismo com o m??rito da decis??o hostilizada, para o qual os embargos de declara????o n??o s??o instrumento processual adequado, porquanto n??o se admite, nesta via, uma nova valora????o da causa. Embargos acolhidos em parte."
    },
    {
        "lawsuit_class": " Apela????o Criminal / Recepta????o",
        "lawsuit_judge": " Camargo Aranha Filho",
        "lawsuit_city": " Araras",
        "trial_date": "04-10-2021",
        "decision_short": " APELA????O. RECEPTA????O DOLOSA. Artigo 180, caput, do C??digo Penal. Senten??a condenat??ria. Pleito de reforma da r. senten??a. Alega????o de fragilidade da prova. Irresigna????o n??o acolhida. Materialidade e autoria comprovadas pelo conjunto probat??rio. Declara????es da v??tima. Em il??citos patrimoniais, a palavra da v??tima ?? de suma valia. Testemunhos de agentes policiais. Inquestion??vel efic??cia probat??ria especialmente quando prestado em ju??zo, sob a garantia do contradit??rio. Circunst??ncias da investidura na posse da coisa que revela a ci??ncia da origem esp??ria do bem. Condena????o mantida. Dosimetria da pena que, entretanto, comporta reparo. Inqu??ritos policiais ou a????es penais em curso n??o se prestam para a valora????o das circunst??ncias judiciais em desfavor do r??u, sendo indispens??vel a certid??o indicando condena????o com tr??nsito em julgado. S??mula n. 444, do Colendo Superior Tribunal de Justi??a. Pena-base reduzida ao m??nimo legal. Regime inicial de cumprimento abrandado para o aberto. Substitui????o da pena privativa de liberdade por restritivas de direitos. Senten??a reformada em parte. RECURSO PARCIALMENTE PROVIDO. "
    },
    {
        "lawsuit_class": " Apela????o C??vel / Desapropria????o por Utilidade P??blica / DL 3.365/1941",
        "lawsuit_judge": " Oswaldo Luiz Palu",
        "lawsuit_city": " Guarulhos",
        "trial_date": "24-09-2021",
        "decision_short": " RETRATA????O. Desapropria????o. Embargos ?? Execu????o. Impugna????o aos c??lculos. Pagamento integral do cr??dito. N??o incid??ncia da Lei n?? 11.960/09.1. Colendo STF que julgou em 20.09.2017 o Tema 810 (RE 870.947/SE), que trata da validade da corre????o monet??ria e dos juros morat??rios incidentes sobre as condena????es impostas ?? Fazenda P??blica. No tocante ??s rela????es jur??dicas n??o tribut??rias, o entendimento ?? claro quanto ?? constitucionalidade dos juros morat??rios da caderneta de poupan??a, nos termos da Lei n?? 11.960/09, e quanto ?? inconstitucionalidade dos ??ndices de corre????o monet??ria da caderneta de poupan??a, com aplica????o do ??ndice IPCA-E.2. Cr??dito oriundo de a????o de desapropria????o, regulada por lei espec??fica, tanto no que concerne ao pedido principal quanto a seus consect??rios legais, e que n??o admite o regramento dado pela Lei 9.494/97, seja em sua reda????o original, seja pela reda????o dada pela Lei n?? 11.960/2009, em estrita conson??ncia com o entendimento proferido pelo C. Superior Tribunal de Justi??a em repercuss??o geral nos autos do REsp n?? 1.495.146/MG, Tema 905, DJe 02/03/2018, que assim disp??e: \"(...) 3.1.2. Condena????es judiciais referentes a desapropria????es diretas e indiretas. No ??mbito das condena????es judiciais referentes a desapropria????es diretas e indiretas existem regras espec??ficas, no que concerne aos juros morat??rios e compensat??rios, raz??o pela qual n??o se justifica a incid??ncia do art. 1??-F da Lei 9.494/97 (com reda????o dada pela Lei n?? 11.960/2009), nem para compensa????o da mora nem para remunera????o do capital. (...)\" 3. Ac??rd??o mantido. Retrata????o n??o realizada. "
    },
    {
        "lawsuit_class": " Apela????o Criminal / Estelionato",
        "lawsuit_judge": " Grassi Neto",
        "lawsuit_city": " Pirapozinho",
        "trial_date": "30-09-2021",
        "decision_short": " Extin????o da punibilidade ???  Fatos ocorridos antes da entrada em vigor da Lei n. 12.234/10 ???  Senten??a condenat??ria com tr??nsito em julgado apenas para a acusa????o ???  Flu??ncia, entre a data de publica????o da senten??a recorrida e o julgamento do recurso, de lapso de tempo superior ao prazo prescricional obtido a partir do quantum de pena aplicado, dentre os previstos no rol do art. 109 do CP ???  Ocorr??ncia da prescri????o intercorrente da pretens??o punitiva nos termos do art. 110, ?? 1??, do CPEm se cuidando de senten??a condenat??ria com tr??nsito em julgado apenas para acusa????o, na hip??tese de, entre a data da publica????o da senten??a condenat??ria e a do presente julgamento, ter restado superado o lapso prescricional obtido a partir do quantum de pena aplicado, dentre aqueles previstos no rol do art. 109 do CP, torna-se de rigor a decreta????o da extin????o da punibilidade do r??u, nos termos do art. 110, ?? 1??, do CP, pelo advento da prescri????o intercorrente da pretens??o punitiva. "
    },
    {
        "lawsuit_class": " Apela????o Criminal / Furto Qualificado",
        "lawsuit_judge": " Gilda  Alves Barbosa  Diodatti",
        "lawsuit_city": " Piracaia",
        "trial_date": "29-09-2021",
        "decision_short": " PRESCRI????O DA PRETENS??O PUNITIVA RETROATIVA. DECLARA????O IMPERATIVA. O apelante Brendo foi condenado pela pr??tica dos crimes de viola????o de domic??lio e furto tentado qualificado, respectivamente, ??s penas de seis meses de deten????o, e de oito meses de reclus??o e tr??s dias-multa, cujo lapso prescricional ?? de tr??s anos, reduzido pela metade em raz??o da menoridade relativa dele ?? ??poca dos fatos. Ocorre que, entre a data do recebimento da den??ncia (22/05/2018) e o dia em que a senten??a condenat??ria tornou-se p??blica (19/07/2021), transcorreu tal lapso temporal, ausentes causas interruptivas ou suspensivas da prescri????o. Nesse cen??rio, for??osa ?? a declara????o de extin????o da punibilidade do acusado, pela prescri????o da pretens??o punitiva, retroativa. Declarada extinta a punibilidade de Brendo Luciano Cruz Silva, pela prescri????o da pretens??o punitiva, retroativa. "
    },
    {
        "lawsuit_class": " Apela????o C??vel / Pagamento Atrasado / Corre????o Monet??ria",
        "lawsuit_judge": " Rubens Rihl",
        "lawsuit_city": " S??o Paulo",
        "trial_date": "04-10-2021",
        "decision_short": " JU??ZO DE RETRATA????O ???  Artigo 1.030, inciso II, do C??digo de Processo Civil - Corre????o Monet??ria e Juros de Mora - Julgamento do 1.495.146/MG, Tema 905, pelo STJ - Ado????o do crit??rio pacificado tanto pelo STF quanto pelo STJ nos temas de repercuss??o geral n?? 810 e de recurso repetitivo n??. 905 relativamente aos juros de mora ???  Retorno dos autos nos termos do artigo 1.041, ??2?? do C??digo de Processo Civil.  Adequa????o do julgado, nos termos do art. 1.040, II, do CPC para fins de aplica????o do quanto julgado no Tema n?? 905 - STJ e Tema n?? 810  STF. "
    },
    {
        "lawsuit_class": " Apela????o C??vel / Pens??o",
        "lawsuit_judge": " Osvaldo de Oliveira",
        "lawsuit_city": " S??o Paulo",
        "trial_date": "27-09-2021",
        "decision_short": " SOBRESTAMENTO DE RECURSO ESPECIAL   ???  ARTIGO 1.040, II, DO CPC ???  Juros e corre????o monet??ria ???  Lei n?? 11.960/09 ???  Decis??o proferida no REsp n?? 1.492.221/PR, Tema n?? 905, STJ, DJe 30.10.2019 ??? Julgamento do RE n?? 870.947/SE, Tema n?? 810, STF, DJe 20.11.2017 ???  Embargos de declara????o no RE 870.947/SE que foram rejeitados e afastada a modula????o da decis??o anteriormente proferida ???  Observ??ncia da orienta????o do Superior Tribunal de Justi??a no REsp 1.492.221/PR (Tema n?? 905) e no RE 870.947/SE (Tema 810) ???  Revis??o do julgado acolhida. "
    },
    {
        "lawsuit_class": "Embargos de Declara????o C??vel / Desapropria????o Indireta",
        "lawsuit_judge": "Aroldo Viotti",
        "lawsuit_city": "Porto Ferreira",
        "trial_date": "01-10-2021",
        "decision_short": "Recurso. A????o de Indeniza????o por Apossamento Administrativo (Desapropria????o Indireta) movida contra o DER, em fase de execu????o. D??bito atingido pela morat??ria constitucional do artigo 78 do Ato das Disposi????es Constitucionais Transit??rias. Senten??a que julgou extinta a execu????o (art. 924, inc. II, CPC). D??bito atingido pela morat??ria constitucional do artigo 78 do Ato das Disposi????es Constitucionais Transit??rias. Hip??tese em que deve prevalecer o quanto determinado no t??tulo sob execu????o. Inviabilidade, ademais, de aplica????o do artigo 5?? da Lei Federal n?? 11.960/09, declarado inconstitucional \"por arrastamento\" pelo STF. Ademais, se ?? aplic??vel o artigo 78 do ADCT ?? esp??cie, isto se d?? porque o pagamento, \"ipso facto\", n??o ocorreu no prazo contemplado na parte permanente da Constitui????o, de modo que devem ser computados juros morat??rios sobre as parcelas devidas. Ademais, o STF, na aprecia????o de medida cautelar nas ADIs 2356 e 2362, suspendeu a efic??cia do art. 2?? da EC 30/00. Inaplicabilidade ?? esp??cie da S??mula Vinculante n?? 17 do STF. N??o h??, ademais, na esp??cie, t??tulo judicial a amparar a pretendida execu????o contra os autores, ora exequentes. Princ??pios da economia e da celeridade processuais ininvoc??veis diante da regra do art. 783 do CPC. Eventual saldo credor em favor do executado-apelante dever?? ser apurado em a????o pr??pria. Recurso Extraordin??rio da Autarquia. Autos restitu??dos ?? C??mara pela Egr??gia Presid??ncia da Se????o de Direito P??blico, para os fins do artigo 1.040, II, do CPC. Mat??ria objeto de repercuss??o geral nos autos do Recurso Extraordin??rio n?? 590.751 (Tema n?? 132) e Recurso Extraodin??rio 1.169.289/SC (Tema 1.037). Hip??tese em que o Ac??rd??o recorrido n??o discrepou do entendimento exarado pelo Supremo Tribunal Federal. Restitui????o dos autos ?? Colenda Presid??ncia da Se????o de Direito P??blico deste Tribunal de Justi??a, por n??o se tratar de caso de poss??vel retrata????o nos termos e para os fins do artigo 1.040, inciso II, do CPC."
    }
]
```
