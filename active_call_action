import xapi from 'xapi';

const zeroCalls = 0;
const myUrl = 'https://hotconcepts.com.au/wp-content/uploads/2013/12/Blank-Red-Webpage-Background.jpg';


// Process updated Active Call COUNT data
function checkCallCount(amount) {
   console.log('DEBUG - Active Calls Detected: ' + amount);
   if (amount > zeroCalls) {
      console.log('DEBUG - Turn LED Red');
      xapi.Command.UserInterface.LedControl.Color.Set({ Color: 'Red' });
      console.log('DEBUG - Display RED webpage on screen');
      xapi.command('UserInterface WebView Display', {
        Title: 'Welcome Page',
        Url: myUrl
      });

   }else if(amount == zeroCalls){
     console.log('DEBUG - Turn LED off');
     xapi.Command.UserInterface.LedControl.Color.Set({ Color: 'Off' });
     console.log('DEBUG - Display RED webpage on screen');
     xapi.command('UserInterface WebView Clear');
   }
}


// Get updated Active Call COUNT value
xapi.status.on('SystemUnit State NumberOfActiveCalls', (numberOfActiveCalls) => checkCallCount(numberOfActiveCalls)); 
