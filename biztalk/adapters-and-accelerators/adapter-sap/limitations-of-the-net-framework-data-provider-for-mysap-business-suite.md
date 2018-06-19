---
title: .NET Framework Data Provider for mySAP Business Suite の制限事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Data Provider for SAP, limitations of
- .NET Framework Data Provider for mySAP Business Suite, limitations of
ms.assetid: 462e627d-41da-4456-bc62-e8cf7296f5b4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fd4ad3a57e2b762a53582ceb77eb65f23a535fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216474"
---
# <a name="limitations-of-the-net-framework-data-provider-for-mysap-business-suite"></a>.NET Framework Data Provider for mySAP Business Suite の制限事項
次はの既知の制限、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])。  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]セキュリティで保護されたネットワーク接続 (SNC) を使用して SAP システムへの接続をサポートしていません。 SNC の詳細については、次を参照してください。 [SAP システムとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)です。
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はサポートしていません、`DbType`または`Size`のプロパティ、`SAPParameter`です。 代わりに、ユーザーがの値を指定すると、 `SAPParameter`.NET と SAP のデータ型の間に確立したマップに従って .NET データ型に値が内部的にキャストします。  
  
-   SAP データ型のフィールド値の許可されている最大の長さ`CURR`、 `DEC`、および`QUAN`29 桁がします。 SAP は 31 の場所にこれらのデータ型の値ネイティブには、変換先の .NET decimal データ型に 29 桁の制限が適用されます。  
  
-   .NET データ型間のマッピング制限`Double`と SAP`FLTP`データ型に .NET 型に SAP システムからデータを読み取るときにオーバーフロー エラーが発生します。 .NET 型が値までの範囲-1.79769313486232e308 から 1.79769313486232 e 308、SAP と倍精度の 64 ビットの数値を表すことができますが`FLTP`によって型が解析され、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 1.8446744073709552E + 19 を超えることはできません効率的な制限、`FLTP`型は負の値の 1.8446744073709552E + 正 1.8446744073709552E + 19 に 19 の範囲です。  
  
-   基になるクライアント ライブラリによるタイムアウトの処理に関する問題のため、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]コマンドと接続のタイムアウトをサポートしていません。  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]非同期コマンドの動作をサポートしていません。  
  
-   SQL Server Integration Services (SSIS) プロジェクトで使用する場合、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 8000 以上の文字の値が含まれている列のデータの取得に失敗します。 これに基づいて、SSIS の制限のため次に示します。  
  
    -   SSIS 変数内の 4,000 文字より大きい値を指定することはできません。  
  
    -   4000 のワイド文字を超える値はサポートされていません。  
  
    -   1 バイト文字で 8000 を超える値はサポートされていません。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)