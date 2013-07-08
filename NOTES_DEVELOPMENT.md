Code sheet
=============
	python -m SimpleHTTPServer 8080
	ps -ef | less
	ps -ef | grep -i jboss
	w -f
	who
	df --disk space
	run.bat -Djboss.service.binding.set=ports-02
	run.bat --configuration=default_X
	nohup ./run.sh -b 0.0.0.0 -Djboss.service.binding.set=ports-02 &
	Usuario: kaf@banregio.com
	Contraseña: BanregioKAF
	netstat -ao
	netstat -b
	taskkill /F /IM firefox.exe /S 10.1.11.128 /U user /P user
	pscp file user@ip:destiny Viene en el putty
	http://ejohn.org/blog/javascript-micro-templating/
	console.log('console para firebug en js');
	SET IDENTITY_INSERT menu off--ON/OFF
	SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED --with(nolock) para toda la transaccion
	zip -r /home/desarrollo/Documents/PM-backup-20120405.zip ProcessManager-ear.ear
	unzip ProcessManager-ear.ear.zip
	NBTSTAT -A 10.10.10.10 #obtener datos de una ip en red en windows
	$("#{rich:clientId('btnVerDetalleBusSoli')}").insert({ before:$("#{rich:clientId('btnSeleccionarDetenerSol')}")});
	./twiddle.sh -s 192.1.0.86 get "jboss.system:type=Server" Started
	./shutdown.sh -S jnp://192.1.0.86:1099
	Validators
	try{
	  saveOrUpdate();
		banregioEntityManager.flush();
	}catch(org.hibernate.validator.InvalidStateException e){
						org.hibernate.validator.InvalidValue[] invalidValues = e.getInvalidValues();
				        for(org.hibernate.validator.InvalidValue invalidValue : invalidValues) {
				           System.out.println("Invalid Value: #0 "+ invalidValue.getPropertyName());
				        }
				        e.printStackTrace();
					}
	> <a:log popup="false" level="ALL" style="width: 800px; height: 300px;"/>
	1) in jboss-{version}/server/bin/run.bat, somewhere at the end, there is a line like this:
	rem set JAVA_OPTS=-Xdebug -Xrunjdwp:transport=dt_socket,address=8787,server=y,suspend=y %JAVA_OPTS%
	For backup reasons, just start by making a copy of that line, then remove the first 'rem' and change suspend=y to suspend=n. Then you get something like
	rem set JAVA_OPTS=-Xdebug -Xrunjdwp:transport=dt_socket,address=8787,server=y,suspend=y %JAVA_OPTS%
	set JAVA_OPTS=-Xdebug -Xrunjdwp:transport=dt_socket,address=8787,server=y,suspend=n %JAVA_OPTS%
	2) In your IDE debug by connecting to a remote Java application on localhost on port 8787. Then you can start adding break points and run through the processes with the console until the breakpoint is hit. 
	
	Variable entorno de ant en linux en el .profile o .bash_profile
	export ANT_HOME=/home/desarrollo/instaladores/apache-ant-1.8.4
	PATH=$PATH:${ANT_HOME}/bin

	-#{eventContext.set('id', 'id_'.concat(rub.key.id))}
	
	standardjboss.xml en server/default/conf en seccion de "Standard Stateful SessionBean" es la propiedad:
	max-bean-life en segundos
	Port binding en jboss 7 <socket-binding-group name="standard-sockets" default-interface="public" port-offset="100"> el 100 es el default que le sumara
	Component.class
	private Object getValueToInject(In in, String name, Object bean, boolean enforceRequired)
	
	Solicitudes perdidas, clonadas:
	select l.date_,l.token_, l.oldlongvalue_, l.newlongvalue_ from jbpm_variableinstance v
	inner join jbpm_log l on v.id_ = l.variableinstance_
	where l.newlongvalue_ <> l.oldlongvalue_ 
	and v.name_ = 'numeroSolicitud'
	order by l.newlongvalue_, l.oldlongvalue_

	org.jboss.seam.intercept.RootInterceptor

	typeof obtenerTabsConsulta == 'function'
	<!-- arjuna -->
	   <category name="com.arjuna.ats.jta.logging">
	      <priority value="ERROR"/>
	   </category>
	search specific metadata in a table
	select st.name,sep.name,sep.value from sys.extended_properties sep inner join sysobjects so on so.id = sep.major_id inner join sys.tables st on st.object_id = so.id where sep.name = 'Catalogo' order by st.name
	add Extended metadata to a table
	EXEC sys.sp_addextendedproperty @name=N'Catalogo', @value=N'Catalogo' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'tipo_cuenta'

	En conf/jboss-log4j.xml para que no salgan warnings de ejb

	<category name="org.jboss.ejb3.interceptors">
	    <priority value="ERROR" />
	</category>
	En ejb3-interceptors-aop.xml comentar
	<aspect name="InterceptorsFactory" factory="org.jboss.ejb3.interceptors.aop.InterceptorsFactory" scope="PER_INSTANCE"/>
	<advice name="invoke" aspect="InterceptorsFactory"/>

	server.xml en jbossweb.sar
		compression="force" compressionMinSize="512" noCompressionUserAgents="gozilla, traviata" compressableMimeType="text/html,text/xml,image/png,text/css,text/javascript"
		
		compression="on" compressableMimeType="text/html,text/xml,text/css,text/javascript, application/x-javascript,application/javascript"
		
	web.xml de la app:
		<context-param>
			<param-name>org.richfaces.LoadStyleStrategy</param-name>
			<param-value>ALL</param-value>
		</context-param>
	
		<context-param>
			<param-name>org.richfaces.LoadScriptStrategy</param-name>
			<param-value>ALL</param-value>
		</context-param>
 
	<context-param>
		<param-name>org.ajax4jsf.COMPRESS_SCRIPT</param-name>
		<param-value>true</param-value>
	</context-param>
	MWrite in the explorer if it were a notepad: data:text/html, <html contenteditable>
