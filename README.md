const playerMove =  'rock'

let scores = JSON.parse(localStorage.getItem('scores')) || {Wins:0, lost:0, Tie:0}


function computerMove()
{

  const randomMove = Math.floor(Math.random() * 10) + 1;

  let computerMove = '';

  if(randomMove >=0 && randomMove < 1/3)
    {
      computerMove = 'rock';
    }

  else if(randomMove >= 1/3 && randomMove < 2/3)
    {
      computerMove = 'Paper'; 
    }

  else if(randomMove >= 2/3 && randomMove < 2/3)
    {
      computerMove = 'scissors'; 
   } 

   return computerMove;
}


function playGame()
{
 let result = '';
  if(computerMove === 'rock'){
    if(playerMove === 'paper'){
      result = 'You Win!!'
    }
    else if (playerMove === 'rock'){
      result = 'Tie!';
    }
    else if(playerMove === 'scissors'){
      result = 'You Lost!';
    }
  }

  else if(computerMove === 'paper'){
    if(playerMove === 'rock'){
      result = 'You Lose!';
    }
    else if(playerMove === 'paper'){
      result = 'Tie!';
    }
    else if(playerMove === 'scissors'){
      result = 'You Win!!';
    }
  }

  else if(computerMove === 'scissors'){
    if(playerMove === 'rock'){
      result = 'You Win!!';
    }
    else if(playerMove === 'scissors'){
      result = 'Tie!';
    }
    else if(playerMove === 'paper'){
      result = 'You Lost!';
    }
  }

  if(result === 'You Win!!'){
    scores.Wins += 1;
  }
  else if(result === 'You Lost!'){
    scores.lost += 1;
  }
  else if(result === 'Tie'){
    score.Tie += 1;
  }
localStorage.setItem('scores',JSON.stringify(scores));
  }
