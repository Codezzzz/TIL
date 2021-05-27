# React styled components Tip

## Global type 작성

- global에 원하는 css를 작성하기 전에, type 선언

```ts
import "styled-components";
import { colorsType, mediaType } from "./theme";

// and extend them!
declare module "styled-components" {
  export interface DefaultTheme {
    media: mediaType;
    color: colorsType;
  }
}
```

## 사용할 global theme 작성

- default mediaQuery, color적용

```ts
import { DefaultTheme } from "styled-components";

const mediaQuery = (maxWidth: number) => `
  @media (max-width: ${maxWidth}px)
`;

const colors = {
  mainColor: "#0a4297",
};

export type colorsType = typeof colors;

const media = {
  xxxlarge: mediaQuery(2200),
  xxlarge: mediaQuery(1920),
  xlarge: mediaQuery(1440),
  large: mediaQuery(1200),
  medium: mediaQuery(1024),
  small: mediaQuery(768),
  xsmall: mediaQuery(375),
  custom: mediaQuery,
};

export type mediaType = typeof media;

const theme: DefaultTheme = {
  color: { ...colors },
  media: { ...media },
};

export default theme;
```

## 사용법

```ts
interface MainStyledProps {
  data: string;
}

const MAIN = styled.div<MainStyledProps>`
  ${({ theme }) => theme.media.small} {
    color: red;
  }

  color: ${({ theme }) => theme.color.mainColor};
`;
```
