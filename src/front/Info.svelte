<script>  
	import {Navbar, Nav, NavItem, NavLink, NavbarBrand, Dropdown, DropdownToggle, DropdownMenu, DropdownItem,Button} from 'sveltestrap';
</script>


<body>
    <Navbar style="background-color: #6EAA8D; color:white;" light expand="lg" >
		<NavbarBrand href="#/info">INICIO</NavbarBrand>
		<Nav navbar>
			<Dropdown >
				<DropdownToggle nav caret> API </DropdownToggle>
				<DropdownMenu end>
				  <DropdownItem href="https://sos2122-24.herokuapp.com/api/v1/cancerdeaths-stats">Cancerdeaths-Stats</DropdownItem>
				  <DropdownItem divider/>
				  <DropdownItem href="https://sos2122-24.herokuapp.com/api/v2/cancerdeaths-stats">Cancerdeaths-Stats-V2</DropdownItem>
				  <DropdownItem divider/>
				  <DropdownItem href="https://sos2122-24.herokuapp.com/api/v2/pneumonia-stats">Pneumonia-Stats-v2</DropdownItem>
				  <DropdownItem divider/>
				  <DropdownItem href="https://sos2122-24.herokuapp.com/api/v1/pneumonia-stats">Pneumonia-Stats</DropdownItem>
				  <DropdownItem divider/>
				  <DropdownItem href="./api/v1/air-pollution-stats">Airpollution-Stats</DropdownItem>
				</DropdownMenu>
            </Dropdown>
              
            <Dropdown>
				<DropdownToggle nav caret> FRONT-END </DropdownToggle>
				<DropdownMenu end>
				  <DropdownItem href="./#/Cancerdeaths-stats">Cancerdeaths FRONT-END</DropdownItem>
				  <DropdownItem divider/>
				  <DropdownItem href="./#/Pneumonia-stats">Pneumonia FRONT-END</DropdownItem>
				  <DropdownItem divider/>
				  <DropdownItem href="#/air-pollution-stats">AirPollution FRONT-END</DropdownItem>
				</DropdownMenu>
			  </Dropdown>
			  
		  <Dropdown >
			<DropdownToggle nav caret> Gráficas </DropdownToggle>
			<DropdownMenu end>
			  <DropdownItem href="./#/cancerdeaths-graph">Cancerdeaths-Stats</DropdownItem>
			  <DropdownItem divider/>
			  <DropdownItem href="./#/cancerdeaths-graph-C3">Cancerdeaths-Stats-C3</DropdownItem>
			  <DropdownItem divider/>
			  <DropdownItem href="./#/graphpneumonia">Pneumonia-Stats</DropdownItem>
			  <DropdownItem divider/>
			  <DropdownItem href="#/graphAirPollution">AirPollution-Stats</DropdownItem>
			  <DropdownItem divider/>
            	<DropdownItem href="./#/graph">Gráfica común</DropdownItem>
			</DropdownMenu>
		  </Dropdown>
		  <!--<NavItem>
			<NavLink style="float:right; margin:left;" href="#/about">Acerca de</NavLink>
		  </NavItem>-->
		</Nav>
	</Navbar>
  </body>
<main>
    <h1>SOS2122-24</h1>

    <h3>Team</h3>
    <p>- <a href="https://github.com/Rgm13">Raúl Gómez Morales</a>(fuente de datos: <a href="https://ourworldindata.org/cancer#deaths-from-cancer">Cancerdeaths-stats</a>)</p>
    <p>- <a href="https://github.com/Lauramartinezsanchez">Laura Martínez Sánchez </a> (fuente de datos: <a href="https://ourworldindata.org/pneumonia">Pneumonia-stats</a>)</p>
    <p>- <a href="https://github.com/AliciaCamposCastello">Alicia Campos Castelló</a>(fuente de datos: AirPollution-stats)</p>
    <br>
    <h3>Project description:</h3> Nuestras fuentes de información esta orientadas a analizar la relación que existe entre la tasa de muertes por neumonia, la tasa de muertes por cancer y la contaminacion del aire en interiores. 
    <br><br>
    <h3>Repository:</h3><a href="https://github.com/gti-sos/SOS2122-24.git">gti-sos/SOS2122-24</a>
    <br><br>
    <h3>URL:</h3><a href="http://sos2122-24.herokuapp.com">http://sos2122-24.herokuapp.com</a>
    <br><br>
    <h3>Documentos POSTMAN:</h3>
    <p>- <a href="./api/v1/cancerdeaths-stats/docs">https://sos2122-24.herokuapp.com/api/v1/cancerdeaths-stats/docs </a>(developed by <a href="https://github.com/Rgm13">Raúl Gómez Morales</a>)</p>
	<p>- <a href="./api/v2/cancerdeaths-stats/docs">https://sos2122-24.herokuapp.com/api/v2/cancerdeaths-stats/docs </a>(developed by <a href="https://github.com/Rgm13">Raúl Gómez Morales</a>)</p>
    <p>- <a href="https://sos2122-24.herokuapp.com/api/v1/pneumonia-stats/docs">https://sos2122-24.herokuapp.com/api/v1/pneumonia-stats/docs </a>(developed by <a href="https://github.com/Lauramartinezsanchez">Laura Martínez Sánchez</a>)</p>
	<p>- <a href="https://sos2122-24.herokuapp.com/api/v2/pneumonia-stats/docs">https://sos2122-24.herokuapp.com/api/v2/pneumonia-stats/docs </a>(developed by <a href="https://github.com/Lauramartinezsanchez">Laura Martínez Sánchez</a>)</p>
    <p>- <a href="https://sos2122-24.herokuapp.com/api/v1/air-pollution-stats/docs">https://sos2122-24.herokuapp.com/api/v1/air-pollution-stats/docs </a>(developed by <a href="https://github.com/AliciaCamposCastello">Alicia Campos Castelló</a>)</p>
    <br>
	<h3>APIS:</h3>
	<p>- <a href="https://sos2122-24.herokuapp.com/api/v1/cancerdeaths-stats">https://sos2122-24.herokuapp.com/api/v1/cancerdeaths-stats </a>(developed by <a href="https://github.com/Rgm13">Raúl Gómez Morales</a>)</p>
	<p>- <a href="https://sos2122-24.herokuapp.com/api/v2/cancerdeaths-stats">https://sos2122-24.herokuapp.com/api/v2/cancerdeaths-stats </a>(developed by <a href="https://github.com/Rgm13">Raúl Gómez Morales</a>)</p>
	<p>- <a href="https://sos2122-24.herokuapp.com/api/v1/pneumonia-stats">https://sos2122-24.herokuapp.com/api/v1/pneumonia-stats </a>(developed by <a href="https://github.com/Lauramartinezsanchez">Laura Martínez Sánchez</a>)</p>
	<p>- <a href="https://sos2122-24.herokuapp.com/api/v2/pneumonia-stats">https://sos2122-24.herokuapp.com/api/v2/pneumonia-stats </a>(developed by <a href="https://github.com/Lauramartinezsanchez">Laura Martínez Sánchez</a>)</p>
	<p>- <a href="https://sos2122-24.herokuapp.com/api/v1/air-pollution-stats">https://sos2122-24.herokuapp.com/api/v1/air-pollution-stats </a>(developed by <a href="https://github.com/AliciaCamposCastello">Alicia Campos Castello</a>)</p>
    <br>
    <h3>FRONT-END:</h3>
	<p>- <a href="#/Cancerdeaths-stats">https://sos2122-24.herokuapp.com/#/Cancerdeaths-stats </a>(developed by <a href="https://github.com/Rgm13">Raúl Gómez Morales</a>)</p>
	<p>- <a href="#/Pneumonia-stats">https://sos2122-24.herokuapp.com/#/Pneumonia-stats </a>(developed by <a href="https://github.com/Lauramartinezsanchez">Laura Martínez Sánchez</a>)</p>
	<p>- <a href="#/air-pollution-stats">https://sos2122-24.herokuapp.com/#/air-pollution-stats </a>(developed by <a href="https://github.com/AliciaCamposCastello">Alicia Campos Castello</a>)</p>
    <br>
    <h3>GÁFRICAS:</h3>
    <p>- <a href="./#/cancerdeaths-graph">https://sos2122-24.herokuapp.com/#/cancerdeaths-graph </a>(developed by <a href="https://github.com/Rgm13">Raúl Gómez Morales</a>)</p>
	<p>- <a href="./#/cancerdeaths-graph-C3">https://sos2122-24.herokuapp.com/#/cancerdeaths-graph-C3 </a>(developed by <a href="https://github.com/Rgm13">Raúl Gómez Morales</a>)</p>
    <p>- <a href="./#/graphpneumonia">https://sos2122-24.herokuapp.com/#/graphpneumonia </a>(developed by <a href="https://github.com/Lauramartinezsanchez">Laura Martínez Sánchez</a>)</p>
	<p>- <a href="./#/graphbillboard">https://sos2122-24.herokuapp.com/#/graphbillboard </a>(developed by <a href="https://github.com/Lauramartinezsanchez">Laura Martínez Sánchez</a>)</p>
    <p>- <a href="#/air-pollution-stats">https://sos2122-24.herokuapp.com/#/air-pollution-stats </a>(developed by <a href="https://github.com/AliciaCamposCastello">Alicia Campos Castello</a>)</p>
	<p>- <a href="./#/graph">https://sos2122-24.herokuapp.com/#/graph </a>(developed by <a href="https://github.com/gti-sos/SOS2122-24">SOS2122-24</a>)</p>
</main>
<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
    h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>
