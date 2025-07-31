# USD-to-BGN
Convert USD to BGN
async function convertUSDToBGN(usdAmount) {
  try {
    const response = await fetch('https://api.exchangerate-api.com/v4/latest/USD');
    const data = await response.json();

    const rateBGN = data.rates.BGN;
    const bgnAmount = usdAmount * rateBGN;

    console.log(`${usdAmount} USD = ${bgnAmount.toFixed(2)} BGN`);
    return bgnAmount;
  } catch (error) {
    console.error('Грешка при взимане на валутния курс:', error);
  }
}

// Пример: конвертиране на 100 USD
convertUSDToBGN(100);
