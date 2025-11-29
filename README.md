# giimport SurveyBot from './src/bot/SurveyBot.js';

(async () => {
  const bot = new SurveyBot({ headless: false });

  await bot.initialize();

  await bot.startSurvey("https://example.com/survey", {
    readySelector: "#start"
  });

  await bot.fillForm([
    { action: 'type', selector: '#name', value: 'Kevin' },
    { action: 'type', selector: '#email', value: 'demo@test.com' },
    { action: 'click', selector: '#next' }
  ]);

  await bot.submitSurvey('#submit');

  await bot.close();
})();
