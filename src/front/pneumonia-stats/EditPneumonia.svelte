<script>

    export let params={};
    import {pop} from 'svelte-spa-router';
    import { onMount } from 'svelte';
    import {Button} from 'sveltestrap';
    import Table from 'sveltestrap/src/Table.svelte';
    import Alert from 'sveltestrap/src/Alert.svelte';
    import {Navbar, Nav, NavItem, NavLink, NavbarBrand, Dropdown, DropdownToggle, DropdownMenu, DropdownItem} from 'sveltestrap';
    
    
    let pneumonia={};

    let checkMSG = "";
    let visible = false;
    let color = "danger";

    
    let updatedCountry;
    let updatedYear;
    let updatedAgesZeroFifty;
    let updatedAgesFiftySeventy;
    let updatedAgesSeventy;

    onMount(getPneumonia);

	async function getPneumonia(){
		console.log("fetching pneumonia ....");
		const res= await fetch("https://sos2122-24.herokuapp.com/api/v2/pneumonia-stats/" +params.country +"/"+params.year);
		if(res.ok){
			const data= await res.json();
			pneumonia=data;
			updatedCountry=pneumonia.country;
            updatedYear=pneumonia.year;
            updatedAgesZeroFifty=pneumonia.ages_zero_fifty;
            updatedAgesFiftySeventy=pneumonia.ages_fifty_seventy;
            updatedAgesSeventy=pneumonia.ages_seventy;
		}else{
            Fallos(res.status,params.country);
            pop();
        }
	}

    async function EditPneumonia(){
        console.log("Updating Pneumonia...."+updatedCountry);
        const res = await fetch("https://sos2122-24.herokuapp.com/api/v2/pneumonia-stats/"+params.country +"/"+params.year,
			{
				method: "PUT",
				body: JSON.stringify({
                    country: updatedCountry,
                    year: updatedYear,
                    ages_zero_fifty: updatedAgesZeroFifty,
                    ages_fifty_seventy: updatedAgesFiftySeventy,
                    ages_seventy: updatedAgesSeventy
                }),
				headers: {
					"Content-Type": "application/json"
				}
			});
            color="success";
			checkMSG="Se ha editado correctamente";
			visible="true";
            //window.alert("Se ha editado correctamente"); 
    }
    async function Fallos(code,entrada){
        
        let msg;
        if(code == 404){
            msg = "No se encuentra "+entrada
        }
        if(code == 400){
            msg = "solicitud incorrecta"
        }
        if(code == 409){
            msg = "El dato introducido ya existe"
        }
        if(code == 401){
            msg = "No autorizado"
        }
        if(code == 405){
            msg = "Método no permitido"
        }
        window.alert(msg)
            return;
    }



    

</script>

<main>
    <Navbar style="background-color: #6EAA8D; color:white;" light expand="lg" >
		<NavbarBrand href="#/info">INICIO</NavbarBrand>
		<Nav navbar>
			<Dropdown >
				<DropdownToggle nav caret> API </DropdownToggle>
				<DropdownMenu end>
				  <DropdownItem href="./api/v1/cancerdeaths-stats">Cancerdeaths-Stats</DropdownItem>
				  <DropdownItem divider/>
				  <DropdownItem href="https://sos2122-24.herokuapp.com/api/v2/pneumonia-stats">Pneumonia-Stats</DropdownItem>
				  <DropdownItem divider/>
				  <DropdownItem href="./api/v1/air-pollution-stats">Airpollution-Stats</DropdownItem>
				</DropdownMenu>
            </Dropdown>
              
            <Dropdown>
				<DropdownToggle nav caret> FRONT-END </DropdownToggle>
				<DropdownMenu end>
				  <DropdownItem href="./#/Cancerdeaths-stats">Cancerdeaths FRONT-END</DropdownItem>
                  <DropdownItem divider/>
				  <DropdownItem href="./#/Pneumonia-stats">Pneumonia FRONT_END</DropdownItem>
                  <DropdownItem divider/>
				  <DropdownItem href="#/air-pollution-stats">AirPollution FRONT-END</DropdownItem>
				</DropdownMenu>
			  </Dropdown>
			  
			  <Dropdown >
				<DropdownToggle nav caret> Gráficas </DropdownToggle>
				<DropdownMenu end>
				  <DropdownItem href="./#/cancerdeaths-graph">Cancerdeaths-Stats</DropdownItem>
				  <DropdownItem href="./#/graphpneumonia">Pneumonia-Stats</DropdownItem>
                  <DropdownItem href="./#/graphbillboard">Pneumonia-Stats-Billboard</DropdownItem>
				  <DropdownItem href="#/graphAirPollution">AirPollution-Stats</DropdownItem>
                  <DropdownItem divider/>
                  <DropdownItem href="./#/graph">Grafica comun</DropdownItem>
				</DropdownMenu>
			  </Dropdown>
		  <!--<NavItem>
			<NavLink style="float:right; margin:left;" href="#/about">Acerca de</NavLink>
		  </NavItem>-->
		</Nav>
	</Navbar>
    <h1> Editar "{params.country}" </h1>
    <Alert color={color} isOpen={visible} toggle={() => (visible = false)}>
		{#if checkMSG}
			{checkMSG}
		{/if}
	</Alert>
    {#await pneumonia}
    loading
        {:then pneumonia}
    
        <Table bordered>
            <thead>
                <tr>
                    <th>País</th>
                    <th>Año</th>
                    <th>Muertes 0-50 años</th>
                    <th>Muertes 50-70 años</th>
                    <th>Muertes 70 años</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>{params.country}</td>
                    <td>{updatedYear}</td>
                    <td><input bind:value="{updatedAgesZeroFifty}"></td>
                    <td><input bind:value="{updatedAgesFiftySeventy}"></td>
                    <td><input bind:value="{updatedAgesSeventy}"></td>
    
                    <td><Button outline color="primary" on:click="{EditPneumonia}">
                        Editar
                        </Button>
                    </td>
                </tr>                
            </tbody>
        </Table>
    
    {/await}
    <Button outline color="secondary" on:click= "{pop}">Volver</Button> 
</main>