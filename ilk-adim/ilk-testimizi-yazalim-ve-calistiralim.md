# İlk Testimizi Yazalım ve Çalıştıralım

İlk testimizi oluşturmak için HelloWorld adında bir dosya oluşturalım. Bunu src klasörü altında **HelloWorld.js** oluşturarak ilerleyebiliriz.

İçeriğini alttaki kod bloğu ile dolduralım.

```jsx
import React from 'react';

function HelloWorld() {
  return (
    <div>
      <h1>Hello World</h1>
    </div>
  );
}

export default HelloWorld;
```

Daha sonra, test dosyamızı(**HelloWorld.test.js**) aşağıdaki gibi oluşturuyoruz:

```jsx
import React from 'react';
import { render, screen } from '@testing-library/react';
import HelloWorld from './HelloWorld';

test('renders hello world text', () => {
  render(<HelloWorld />);
  const helloWorldElement = screen.getByText(/hello world/i);
  expect(helloWorldElement).toBeInTheDocument();
});
```

Bu test dosyasında, `render()` fonksiyonunu kullanarak HelloWorld bileşenini render ediyoruz. Daha sonra, `screen.getByText()` fonksiyonunu kullanarak "hello world" metnini içeren bileşen öğesini alıyoruz. Son olarak, `expect()` fonksiyonunu kullanarak, helloWorldElement'in belgeye eklenip eklenmediğini doğruluyoruz.

Bu örnekteki test, HelloWorld bileşeninin "Hello World" metnini içerip içermediğini kontrol eder. Testimizi çalıştırmak için, terminalde aşağıdaki komutu çalıştırabiliriz:

```bash
npm test
```

Bu komut, testleri otomatik olarak çalıştırır ve sonuçları raporlar. Testimiz başarılı olursa, aşağıdaki gibi bir çıktı alırız:

```bash
PASS  src/HelloWorld.test.js
  ✓ renders hello world text (30 ms)

Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total

```

Bu örnekteki test, Jest ve React Testing Library'nin temel kullanımını gösterir. Bu araçlar, daha karmaşık bileşenler ve senaryolar için de ileride kullanacağız.
