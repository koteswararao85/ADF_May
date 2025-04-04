<jaxb:bindings xmlns:jaxb="https://jakarta.ee/xml/ns/jaxb"
	xmlns:xsd="http://www.w3.org/2001/XMLSchema"
	version="3.0">
	<bindings schemaLocation="../xsd/ArticleMaster.xsd">
		<bindings>
			<namespace:prefix name="sapa" />
		</bindings>
		<bindings node="//xs:complexType[@name='ArticleMaster']">
			<annox:annotate>
				<annox:annotate annox:class="javax.xml.bind.annotation.XmlRootElement"
					name="ArticleMaster" namespace="/com/wba/rxint/sap/articlemaster/event/xml">
				</annox:annotate>
			</annox:annotate>
		</bindings>
	</bindings>
</jaxb:bindings>
