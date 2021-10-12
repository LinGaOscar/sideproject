SpringBoot Project
利用mvn clean install 初始
pom.xml 匯入 angular static ouput
<plugin>
  <artifactId>maven-resources-plugin</artifactId>
  <executions>
	<execution>
	  <id>copy-resources</id>
	  <phase>validate</phase>
	  <goals>
		<goal>copy-resources</goal>
	  </goals>
	  <configuration>
		<outputDirectory>${basedir}/target/classes/static/</outputDirectory>
		<resources>
		  <resource>
			<directory>${basedir}/../todomvc/static</directory>
		  </resource>
		</resources>
	  </configuration>
	</execution>
  </executions>
</plugin>


Angular Project
在angular.json 內設定"outputPath": "./static"
每次修正更新
	ng build //in cmd

創建
	ng new ProjectName --skip-install
	公司擋npm下載，要複製正常專案內的node_modules
	
start server
	ng serve --open //in cmd ,http://localhost:4200/

stop server
	Ctrl+c //in cmd
	
change serve pory
	ng serve --port 4401 //in cmd
	
創建 
	ng g component | pipe | server <name>
craet component
	ng generate component < name >
	將 component.ts 內 selector 放到app.component.html <selector>
	(ex:<app-title>)
	
關係
	每個html 對應該名稱.ts
	
src
app/ (整個網頁應用程式的 Module、Component、Service 等等都放在這)
	app.module.ts 管理頁面使用元件、模組(ex 雙向綁定 imports: FormsMoudle)
assets(資源檔，用來放images、多國語系…等)
environments(環境設定)
favicon.ico(網站圖示)
index.html(起始頁面)
main.ts (Angular bootstrap 的程式進入點)
polyfills.ts(要符合 IE 或舊版瀏覽器時須做設定)
styles.scss(整個網頁應用程式共用的scss設定檔)
test.ts (test 的程式進入點)

語法html
*ngFor = "let product of products"  
*ngIf = "isTrue"
[(ngModel)]="isValue"     //[(XX)]雙向綁定
(ngModelChange)="isChange($event)" //回傳改變值
(ckick)="onclick()"		//(XX)單向綁定

宣告
isTrue:boolean = True;
isValue:string = "text in line"