<!DOCTYPE html>
<html>
   <head>
      <title>Master Node Projection App</title>
      <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.0/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-KyZXEAg3QhqLMpG8r+8fhAXLRk2vvoC2f3B09zVXn8CA5QIVfZOJ3BCsw2P0p/We" crossorigin="anonymous">
      <meta name="viewport" content="width=device-width, initial-scale=1">
	  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
   </head>
   <style>
      .table>:not(caption)>*>* {
      padding: .5rem .5rem;
      background-color: var(--bs-table-bg);
      border-bottom-width: 1em;
      box-shadow: inset 0 0 0 9999px var(--bs-table-accent-bg);
      padding-top:.5em;
      padding-bottom:.5em;
      }
      .green
      {
      color:green;
      }
      .red
      {
      color:red;
      }
      .tokenEarnings
      {
      color:white;
      background-color:green !important;
      padding:.5em !important;
      }
      .monthlyEarnings
      {
      color:black;
      background-color:yellow !important;
      padding:.5em !important;
      }
      .USD_Earnings
      {
      color:white;
      background-color:black !important;
      padding:.5em !important;
      }
      .Prev_Earnings
      {
      color:white;
      background-color:red !important;
      padding:.5em !important;
      }
      .bottomMargin
      {
      margin-bottom:1em !important;
      }
   </style>
   <style>
      /* Tooltip container */
      .tool-tip {
      position: relative;
      display: inline-block;
      }
      /* Tooltip text */
      .tool-tip .tooltiptext {
      visibility: hidden;
      background-color: black;
      color: #fff;
      text-align: center;
      padding: 5px 0;
      border-radius: 6px;
      /* Position the tooltip text - see examples below! */
      position: absolute;
      z-index: 1;
      bottom: 100%;
      left: 50%;
      margin-left: -60px; /* Use half of the width (120/2 = 60), to center the tooltip */
      }
      /* Show the tooltip text when you mouse over the tooltip container */
      .tool-tip:hover .tooltiptext {
      visibility: visible;
      }
   </style>
   <body style="font-size:1.2em;font-family:Times New Roman">
      <form class="container" id="target" style="margin-top:2em"  >
         <div class="col-xs-6  col-lg-4 col-md-12 " style="float:left">
            <div class="col-lg-12  col-md-6 " style="float:left">
               <div class="col-12"style="display:block;float:right;margin-left:1em">
                  <div  style="display:block;float:right">
                     <label for="months">Months to project:</label>
                     <input id="months" style="margin-bottom:1em" type="number"  name="months"
                        min="1" value="12">
                  </div>
               </div>
			   
               <div class="col-12"style="display:block;float:right;margin-left:1em">
                  <div  style="display:block;float:right">
                     <label for="startingTokens">Tokens starting with:</label>
                     <input id="startingTokens" style="margin-bottom:1em" type="number"  name="startingTokens"
                        min="0" value="3.7742" step="0.0001" >
                  </div>
               </div>
			   
               <div class="col-12"style="display:block;float:right;margin-left:1em">
                  <div  style="display:block;float:right">
                     <label for="tokenName">Token Name:</label>
                     <input id="tokenName" style="margin-bottom:1em" type="text" required  name="tokenName" value="OHM">
                  </div>
               </div>

               <div class="col-12"style="display:block;float:right;margin-left:1em">
                  <div style="display:block;float:right;">
                     <label for="tokenPrice">Token Price:</label>
                     <input id="tokenPrice" style="margin-bottom:1em" type="number"  name="tokenPrice"
                        min="0.1"  step="0.01" value="1062.11">
                  </div>
               </div>
			   
			   <div class="col-12"style="display:block;float:right;margin-left:1em">
                  <div style="display:block;float:right;">
                     <label for="RewardYield">Next Reward Yield:</label>
                     <input id="RewardYield" style="margin-bottom:1em" type="number"  name="RewardYield"
                        min="0.0001"  step="0.0001" value="0.4065">
                  </div>
               </div>
			   
			   
			   <!--
			   <div class="col-12"style="display:block;float:right;margin-left:1em">
                  <div style="display:block;float:right;>
                     <label for="ROI">ROI (5-Day Rate):</label>
                     <input id="ROI" style="margin-bottom:1em" type="number"  name="ROI"
                        min="0.0001"  step="0.0001" value="6.2773">
                  </div>
               </div>
			   
               <div class="col-12" style="display:block;float:right;margin-left:1em">
                  <div class="tool-tip formcheck"  style="display:block;float:right">
                     <span class="tooltiptext">Give yourself a monthly allowance or paycheck.</span>
                     <div   style="float:left">
                        <label for="monthlyAllowance">Monthly Allowance:</label>
                        <input class="form-check-input" id="monthlyAllowance" type="checkbox"  name="monthlyAllowance"
                           value="true">
                     </div>
                  </div>
               </div>
               <div class="col-12"style="display:block;float:right;margin-left:1em">
                  <div style="display:block;float:right;>
                     <label for="allowanceStart">Allowance Month start:</label>
                     <input id="allowanceStart" style="margin-bottom:1em" type="number"  name="allowanceStart"
                        min="1" step="1" value="1">
                  </div>
               </div>
               <div class="col-12"style="display:block;float:right;margin-left:1em">
                  <div style="display:block;float:right;>
                     <label for="allowanceAmount">Allowance Amount(USD):</label>
                     <input id="allowanceAmount" style="margin-bottom:1em" type="number"  name="allowanceAmount"
                        min="0" step="0.01" value="0">
                  </div>
               </div>
			   
			   
			   -->
               <div  style="display:block;float:right;margin-bottom:3em">
                  <br><input style="float:right" class="btn btn-primary mb-2" type="submit">
               </div>
      </form>
      </div>
      </div>
	  
	  
	<div class="container">
		<div class="row col-lg-6">
		<div style="display:block;float:left;margin-left:3em">
		<label >Click these to change price input with current price</label>
			<div>
			  <button class="btn btn-secondary mb-2" id='ohmBTN' > OHM Price </button>

			  <button class="btn btn-secondary mb-2"  id='timeBTN' > TIME Price </button>

           <button class="btn btn-secondary mb-2"  id='klimaBTN' > KLIMA Price </button>
			</div>
		</div>
		
		<div style="display:block;float:left;margin-left:3em">
		<label >USD to selected TOKEN Connverter</label>
			<div>
			    <div style="display:block">
                     <label for="usdAmount">Amount(USD):</label>
                     <input id="usdAmount" style="margin-bottom:1em" type="number"  name="usdAmount"
                        min="0" step="0.01" value="0">
				</div>


				<div>
					<p id="convertedVal"></p>
				</div>
				
				<button class="btn btn-secondary mb-2" id='convertBTN' > Convert </button>

			 
			</div>
		</div>
		
		</div>
	</div>

	  
	  <div class="container" style="margin-top:2em">
		<div class="row col-lg-12">
		  <div id="tableContent" >
		  <table id="t01" class="table">
			<tr>
			  <th>Month/Day Count</th>
			  <th>Token Count</th> 
			  <th>Payout/Value</th>
			</tr>

		 
		  </table>
		  </div>
		</div>
	</div>

   </body>
   
  
    <script>	  
   $('#ohmBTN').click(   function (event)
   {
   event.preventDefault();
	fetch('https://api.coingecko.com/api/v3/coins/olympus?tickers=true&market_data=true&community_data=true&developer_data=true&sparkline=false')
    .then((response) => {
      return response.text();
    })
    .then((myContent) => {
        var market = JSON.parse(myContent);
		//console.log( market);
        var info = market["market_data"]["current_price"]["usd"];
		document.getElementById("tokenName").value = "OHM";
		document.getElementById("tokenPrice").value = info.toFixed(2);
        console.log( info);
    });
	});

   $('#klimaBTN').click(   function (event)
  {
  event.preventDefault();
  fetch('https://api.coingecko.com/api/v3/coins/klima-dao?tickers=true&market_data=true&community_data=true&developer_data=true&sparkline=false')
  .then((response) => {
    return response.text();
  })
  .then((myContent) => {
    var market = JSON.parse(myContent);
    console.log( market);
    var info = market["market_data"]["current_price"]["usd"];
    document.getElementById("tokenName").value = "KLIMA";
    document.getElementById("tokenPrice").value = info.toFixed(4);
    console.log( info);
  });
  });
	
	$('#timeBTN').click(   function (event)
	{
	event.preventDefault();
	fetch('https://api.coingecko.com/api/v3/coins/wonderland?tickers=true&market_data=true&community_data=true&developer_data=true&sparkline=false')
	.then((response) => {
	  return response.text();
	})
	.then((myContent) => {
		var market = JSON.parse(myContent);
		console.log( market);
		var info = market["market_data"]["current_price"]["usd"];
		document.getElementById("tokenName").value = "TIME";
		document.getElementById("tokenPrice").value = info.toFixed(4);
		console.log( info);
	});
	});

	$('#convertBTN').click(   function (event)
   {
   event.preventDefault();
   var tokenPrice = Number(document.getElementById("tokenPrice").value);
   var usdAmount = Number(document.getElementById("usdAmount").value);
   
   var math = Number(usdAmount / tokenPrice).toFixed(4);
   
    document.getElementById("convertedVal").innerHTML = math;
	document.getElementById("startingTokens").value = math;
   });
	
	</script>
  
  
  <script>
    $( "#target" ).submit(function( event ) {
		event.preventDefault();

	var months = Number(document.getElementById("months").value);
	var startingTokens =	Number(document.getElementById("startingTokens").value);
	var tokenPrice = Number(document.getElementById("tokenPrice").value);
	var tokenName = document.getElementById("tokenName").value;
	var RewardYield = document.getElementById("RewardYield").value;
	//var ROI = document.getElementById("ROI").value;

	//var monthlyAllowance =	document.getElementById("monthlyAllowance").checked;
	//var allowanceStart	=	Number(document.getElementById("allowanceStart").value);
	//var allowanceAmount	=	Number(document.getElementById("allowanceAmount").value);

		var tableRows = document.getElementById("t01").rows.length;
		for(var x= tableRows-1;x > 0;x--)
		{
			document.getElementById("t01").deleteRow(x);
		}
		 
	
	var currentDay = Number(1);
	var currentTokens = startingTokens;
		for(var month =1;month <=months;month++)
		{
			//for(var fiveDayPeriods = 1;fiveDayPeriods<=6;fiveDayPeriods++)
			//{}
			
			$("#t01").find('tbody').append("<tr><td class='USD_Earnings' style='text-align:center' colspan='1000'><h2> Month "+month+"</h2></td></tr>");
			
			for(var day = 1;day <= 31;day++)
			{
				for(var rebase = 1;rebase <=3;rebase++)
				{
					if(rebase == 1 && day == 1 && month == 1)
					{
						console.log("Started with " + startingTokens );
						console.log("1st rebase "+ (currentTokens+(currentTokens * (RewardYield*0.01))));
					}
					currentTokens += currentTokens * (RewardYield*0.01);
				}
				
				console.log("month " + month + " - day " + day + " tokens " + currentTokens);
				
				if(month == 1)
				{
				var USD_amount = Number((currentTokens*tokenPrice)).toFixed(2);
					$("#t01").find('tbody').append(
					"<tr><td><span > day "+day+"</span></td>"+
					"<td><span class='Prev_Earnings'>"+ Number(currentTokens).toFixed(4) +"</td>"+
					"<td><span class='tokenEarnings'>"+USD_amount+" USD </span></td>"+
					"</tr>");
				}
				else
				{
				var USD_amount = Number((currentTokens*tokenPrice)).toFixed(2);
					$("#t01").find('tbody').append(
					"<tr><td><span > day "+day+"(day"+currentDay+")</span></td>"+
					"<td><span class='Prev_Earnings'>"+ Number(currentTokens).toFixed(4) +"</td>"+
					"<td><span class='tokenEarnings'>"+USD_amount+" USD </span></td>"+
					"</tr>");
				}
				
				
				currentDay+=Number(1);
			}

		}
	});

	function dailySubmit()
	{

	}
	  
  </script>
   
   
</html>
