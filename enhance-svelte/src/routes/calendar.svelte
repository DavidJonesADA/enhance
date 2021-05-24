<script>
    
    let viewIssue = false

    let openIssue = false

    let openTrelloModal = false

    let longText = ""
    let user = ""
    let type = ""


    function openModal() {
        viewIssue = !viewIssue
    }

    function openTrelloModalFunc() {
        openTrelloModal = !openTrelloModal
    }

    function openIssueModal(leter) {
        openIssue = !openIssue
        if (leter == 'a') {
            user = "louisp52"
            type = "Bug"
            longText = "I was trying to download this spotify version fix and use it in the terminal. Upon testing it wouldn't detect the files. I tried reinstalling spotify and the shell script but it wouldn't detect anything"
        } else {
            user = "Ada"
            type = "Request"
            longText = "There isn't any need to include the file lock, using this version of spotify from my testing didn't result in any of this happening. I don't think this is needed."
        }
    }
</script>


{#if openIssue}
<div id="modal" style="width: 100vw; height: 100vh; position: absolute;">
    <div style="position: absolute; width: 100vw; height: 100vh; background-color: grey; z-index: 3; opacity: 20%;"></div>
    <div style="position: absolute; width:100%; height: 100%; padding: 20px; display: flex; align-items: center; z-index: 3;">
        <div style="width: 100%; height: 35%; background-color: #fff; border-left: 8px solid #455855; border-top-right-radius: 15px; border-bottom-right-radius: 15px; padding: 15px; display: flex; flex-direction:column">
            <div>
                <div style="color: black; padding: 0.25rem; background-color: #3fb13f; display: inline-block; border-radius: 15px; color: white; margin-right: 0.5rem;">{user}</div>
                <div style="color: black; padding: 0.25rem; background-color: #ff6c6c; display: inline-block; border-radius: 15px; color: white;">{type}</div>
            </div>
            <div style="color: #e2e2e2; margin-top: 0.5rem; padding: 0.25rem; background-color: #455855">
                {longText}
            </div>
            <div style="text-align: center; font-size: 1.25rem; margin-top: 2rem; color: rgb(69, 88, 85)" on:click={openIssueModal}>Done</div>      
        </div>
    </div>
</div>
{/if}

{#if openTrelloModal}
<div id="saveTrello" style="width: 100vw; height: 100vh; position: absolute; display: unset;">
    <div style="position: absolute; width: 100vw; height: 100vh; background-color: grey; z-index: 3; opacity: 40%;"></div>
    <div style="position: absolute; width:100%; height: 100%; padding: 20px; display: flex; align-items: center; z-index: 3;">
        <div style="width: 100%; color: #455855; height: 35%; background-color: #fff; border-left: 8px solid #455855; border-top-right-radius: 15px; border-bottom-right-radius: 15px; padding: 15px; display: flex; flex-direction:column">
            <div style="font-size: 1.25rem; color: #455855; margin-bottom: 0.25rem">Update Trello Board Spotify-Fix</div>
            <div>Move from <b>In Progress</b>:</div>
            <div style="background-color: #ffd17c; font-size: 16px; padding: 0.25rem; display: inline-block; border-radius: 5px;">Check issues for spotify-old-version-fix</div>
            <div>To:</div>
            <select name="cars" id="cars" style="font-size: 16px;border: none; padding: 0.25rem; background-color: #75da74;  border-radius: 5px; -webkit-appearance: none;">
                <option value="volvo">Complete</option>
                <option value="saab">In Progress</option>
            </select>
            <div style="text-align: center; font-size: 1.25rem; margin-top: 2rem; " on:click={openTrelloModalFunc}>Done</div>      
        </div>
    </div>
</div>
{/if}

<div class="calendar-container">
    <div class="calendar-container__header">
      <button class="calendar-container__btn calendar-container__btn--left" title="Previous">
        <i class="icon ion-ios-arrow-back"></i>
      </button>
      <h2 class="calendar-container__title" style="color: white; font-weight: 400; margin-top: 1rem">October 2018</h2>
      <button class="calendar-container__btn calendar-container__btn--right" title="Next">
        <i class="icon ion-ios-arrow-forward"></i>
      </button>
    </div>
    <div class="calendar-container__body">
      <div class="calendar-table">
        <div class="calendar-table__header">
          <div class="calendar-table__row">
            <div class="calendar-table__col">S</div>
            <div class="calendar-table__col">M</div>
            <div class="calendar-table__col">T</div>
            <div class="calendar-table__col">W</div>
            <div class="calendar-table__col">T</div>
            <div class="calendar-table__col">F</div>
            <div class="calendar-table__col">S</div>
          </div>
        </div>
        <div class="calendar-table__body">
          <div class="calendar-table__row">
            <div class="calendar-table__col calendar-table__inactive">
              <div class="calendar-table__item">
                <span>30</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>1</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>2</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>3</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>4</span>
              </div>
            </div>
            <div class="calendar-table__col calendar-table__event">
              <div class="calendar-table__item">
                <span>5</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>6</span>
              </div>
            </div>
          </div>
          <div class="calendar-table__row">
            <div class="calendar-table__col calendar-table__event">
              <div class="calendar-table__item">
                <span>7</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>8</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>9</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>10</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>11</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>12</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>13</span>
              </div>
            </div>
          </div>
          <div class="calendar-table__row">
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>14</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>15</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>16</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>17</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>18</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>19</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>20</span>
              </div>
            </div>
          </div>
          <div class="calendar-table__row">
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>21</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>22</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>23</span>
              </div>
            </div>
            <div class="calendar-table__col calendar-table__today">
              <div class="calendar-table__item">
                <span>24</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>25</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>26</span>
              </div>
            </div>
            <div class="calendar-table__col calendar-table__event calendar-table__event--long calendar-table__event--start">
              <div class="calendar-table__item">
                <span>27</span>
              </div>
            </div>
          </div>
          <div class="calendar-table__row">
            <div class="calendar-table__col calendar-table__event calendar-table__event--long calendar-table__event--end">
              <div class="calendar-table__item">
                <span>28</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>29</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>30</span>
              </div>
            </div>
            <div class="calendar-table__col">
              <div class="calendar-table__item">
                <span>31</span>
              </div>
            </div>
            <div class="calendar-table__col calendar-table__event calendar-table__inactive">
              <div class="calendar-table__item">
                <span>1</span>
              </div>
            </div>
            <div class="calendar-table__col calendar-table__inactive">
              <div class="calendar-table__item">
                <span>2</span>
              </div>
            </div>
            <div class="calendar-table__col calendar-table__inactive">
              <div class="calendar-table__item">
                <span>3</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="events-container">
    <span class="events__title">Upcoming events this month</span>
    <ul class="events__list">

      <li class="events__item" style="display: block;">
          <div style="display: flex; justify-content: space-between; align-items: center; margin-bottom: 1rem;"  >
            <div class="events__item--left" on:click={openModal}>
                <span class="events__name">Check issues for spotify-old-version-fix</span>
                <span class="events__date">Oct 24</span>
            </div>
            <img style="width: 1.5rem; height: 1.5rem" src="../images/chrome_50Qf9Ziy8v.png" alt="dasddsaa" on:click={openTrelloModalFunc}>
          </div>
        
        {#if viewIssue}
        <div style="color: #222741; font-size: 0.90rem; center; display: flex; flex-direction: column;">
            <div style="text-align: center; font-weight: 600; margin-bottom: 0.25rem">Existing Issues</div>
            <div style="color: #222741; font-size: 0.80rem; display: flex; align-items: center; justify-content: space-around; margin-bottom: 0.25rem">
                <div style="max-width: 60%;">Issues reveriting back with macOS catilina</div>
                <div style="margin-left: 1rem; padding: 0.25rem; background-color: #b5ffc2; border-radius: 10px" on:click={() => openIssueModal('a')}>Reveal</div>
            </div>
            <div style="color: #222741; font-size: 0.80rem; display: flex; align-items: center; justify-content: space-around; margin-bottom: 0.25rem">
                <div style="max-width: 60%;">Optimize script by removing lock</div>
                <div style="margin-left: 1rem; padding: 0.25rem; background-color: #b5ffc2; border-radius: 10px" on:click={() => openIssueModal('b')}>Reveal</div>
            </div>
        </div>
        {/if}
      </li>



      <li class="events__item" style="flex-direction: row;">
            <div class="events__item--left">
                <span class="events__name">Push next-js to master</span>
                <span class="events__date">Oct 27</span>
            </div>
            <div>
                <img style="width: 1.5rem; height: 1.5rem;" src="../images/chrome_52qINqGVNK.png" alt="dasddsaa" on:click={openTrelloModalFunc}>
            </div>
      </li>


      <li class="events__item" style="flex-direction: row;">
        <div class="events__item--left">
            <span class="events__name">Check pull requests for opennam-auth-node</span>
            <span class="events__date">Nov 1</span>
        </div>
        <div>
            <img style="width: 1.5rem; height: 1.5rem;" src="../images/chrome_lGoPS9sQw2.png" alt="dasddsaa" on:click={openTrelloModalFunc}>
        </div>
  </li>



    </ul>
  </div>

  <style>
      * {
	 margin: 0;
	 padding: 0;
	 box-sizing: border-box;
}
 html, body {
	 height: 100%;
}
 body {
	 -webkit-font-smoothing: antialiased;
	 font-family: 'Montserrat', sans-serif;
	 text-rendering: optimizeLegibility;
	 background: #fcfcfc;
}
 .mock-up-link {
	 display: none;
}
 @media (min-width: 768px) {
	 .mock-up-link {
		 display: block;
	}
}
 .main-container-wrapper {
	 background-color: #f8fafa;
	 min-width: 320px;
	 min-height: 568px;
	 max-width: 414px;
	 overflow-y: auto;
}
 @media (min-width: 415px) {
	 .main-container-wrapper {
		 -moz-box-shadow: 0px 32px 47px rgba(32, 23, 23, 0.09);
		 -webkit-box-shadow: 0px 32px 47px rgba(32, 23, 23, 0.09);
		 box-shadow: 0px 32px 47px rgba(32, 23, 23, 0.09);
		 margin: 24px auto;
	}
}
 header {
	 background-color: #fff;
	 display: flex;
	 height: 58px;
	 justify-content: space-between;
	 overflow: hidden;
	 position: relative;
}
 .header__btn {
	 background-color: #86d8c9;
	 border: 2px solid #fff;
	 border-radius: 50%;
	 -moz-box-shadow: 0 2px 2px rgba(0, 0, 0, 0.1);
	 -webkit-box-shadow: 0 2px 2px rgba(0, 0, 0, 0.1);
	 box-shadow: 0 2px 2px rgba(0, 0, 0, 0.1);
	 cursor: pointer;
	 height: 80px;
	 padding-top: 18px;
	 position: absolute;
	 top: -25px;
	 width: 80px;
}
 .header__btn:hover, .header__btn:focus {
	 background: #67cebb;
	 transition: all 0.3s ease-in;
	 outline: none;
}
 .header__btn .icon {
	 display: inline-block;
}
 .header__btn--left {
	 left: -25px;
	 padding-left: 38px;
	 text-align: left;
}
 .header__btn--right {
	 padding-right: 32px;
	 right: -25px;
	 text-align: right;
}
 .calendar-container {
	 margin-bottom: 24px;
}
 .calendar-container__header {
	 display: flex;
	 justify-content: space-between;
}
 .calendar-container__btn {
	 background: transparent;
	 border: 0;
	 cursor: pointer;
	 font-size: 16px;
	 outline: none;
	 color: #e9e8e8;
}
 .calendar-container__btn:hover, .calendar-container__btn:focus {
	 color: #9faab7;
	 transition: all 0.3s ease-in;
}
 .calendar-container__title {
	 color: #222741;
	 font-size: 20px;
	 font-weight: 700;
}
 .calendar-table {
	 margin-top: 12px;
	 width: 100%;
}
 .calendar-table__item {
	 border: 2px solid transparent;
	 border-radius: 50%;
	 color: #fff;
	 font-size: 12px;
	 font-weight: 700;
	 width: 100%;
	 height: 100%;
	 display: flex;
	 align-items: center;
	 justify-content: center;
	 cursor: pointer;
}
 .calendar-table__item:hover {
	 background: #f3c1ff;
	 -moz-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 -webkit-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 transition: 0.2s all ease-in;
}
 .calendar-table__row {
	 display: flex;
	 justify-content: center;
}
 .calendar-table__header {
	 border-bottom: 2px solid #f2f6f8;
	 margin-bottom: 4px;
}
 .calendar-table__header .calendar-table__col {
	 display: inline-block;
	 color: #99a4ae;
	 font-size: 12px;
	 font-weight: 700;
	 padding: 12px 3px;
	 text-align: center;
	 text-transform: uppercase;
	 width: 40px;
	 height: 38px;
}
 @media (min-width: 360px) {
	 .calendar-table__header .calendar-table__col {
		 width: 46px;
	}
}
 @media (min-width: 410px) {
	 .calendar-table__header .calendar-table__col {
		 width: 54px;
	}
}
 .calendar-table__body .calendar-table__col {
	 width: 40px;
	 height: 42px;
	 padding-bottom: 2px;
}
 @media (min-width: 360px) {
	 .calendar-table__body .calendar-table__col {
		 width: 46px;
		 height: 48px;
	}
}
 @media (min-width: 410px) {
	 .calendar-table__body .calendar-table__col {
		 width: 54px;
		 height: 56px;
	}
}
 .calendar-table__today .calendar-table__item {
	 border-color: #fefefe;
	 background-color: #e88aff;
	 -moz-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 -webkit-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
}
 .calendar-table__event .calendar-table__item {
	 background-color: #66dcec;
	 border-color: #fefefe;
	 -moz-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 -webkit-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 color: #fff;
}
 .calendar-table__event--long {
	 overflow-x: hidden;
}
 .calendar-table__event--long .calendar-table__item {
	 border-radius: 0;
	 border-width: 2px 0;
}
 .calendar-table__event--start .calendar-table__item {
	 border-left: 2px solid #fff;
	 border-radius: 50% 0 0 50%;
}
 .calendar-table__event--start.calendar-table__col:last-child .calendar-table__item {
	 border-width: 2px;
}
 .calendar-table__event--end .calendar-table__item {
	 border-right: 2px solid #fff;
	 border-radius: 0 50% 50% 0;
}
 .calendar-table__event--end.calendar-table__col:first-child .calendar-table__item {
	 border-width: 2px;
}
 .calendar-table__inactive .calendar-table__item {
	 color: #dcdce3;
	 cursor: default;
}
 .calendar-table__inactive .calendar-table__item:hover {
	 background: transparent;
	 box-shadow: none;
}
 .calendar-table__inactive.calendar-table__event .calendar-table__item {
	 color: #fff;
	 opacity: 0.25;
}
 .calendar-table__inactive.calendar-table__event .calendar-table__item:hover {
	 background: #66dcec;
	 -moz-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 -webkit-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
}
 .events-container {
	 padding: 0 15px;
}
 .events__title {
	 color: #fff;
	 display: inline-block;
	 font-size: 16px;
	 font-weight: 300;
	 margin-bottom: 16px;
}
 .events__tag {
	 background: #66dcec;
	 border: 2px solid #fefefe;
	 -moz-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 -webkit-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.1);
	 border-radius: 20px;
	 color: #fff;
	 font-size: 10px;
	 font-weight: 600;
	 width: 60px;
	 margin-left: 16px;
	 padding: 5px 2px;
	 text-align: center;
}
 .events__tag--highlighted {
	 background: #fdca40;
}
 .events__item {
	 background: #fff;
	 border-left: 8px solid #86d8c9;
	 border-radius: 2px;
	 -moz-box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.05);
	 -webkit-box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.05);
	 box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.05);
	 padding: 15px 16px;
	 display: flex;
     flex-direction: column;
	 justify-content: space-between;
	 align-items: center;
	 margin-bottom: 16px;
}
 .events__item--left {
	 width: calc(100% - 76px);
}
 .events__name {
	 font-size: 12px;
	 font-weight: 700;
	 color: #222741;
	 display: block;
	 margin-bottom: 6px;
}
 .events__date {
	 font-size: 12px;
	 color: #9faab7;
	 display: inline-block;
}
 
  </style>