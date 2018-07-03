---
title: .NET Framework Data Provider for mySAP Business Suite の制限事項 |Microsoft Docs
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
ms.openlocfilehash: 9efcf7fb18471c92c504e08df43482fbc64064d2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999819"
---
# <a name="limitations-of-the-net-framework-data-provider-for-mysap-business-suite"></a>.NET Framework Data Provider for mySAP Business Suite の制限事項
次の制限事項を呼びます、 [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] ([!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)])。  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はセキュリティで保護されたネットワーク接続 (SNC) を使用して SAP システムへの接続をサポートしていません。 SNC の詳細については、次を参照してください。 [SAP システムとアダプター間のセキュリティ](../../adapters-and-accelerators/adapter-sap/security-between-the-sap-system-and-the-adapter.md)します。
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]はサポートしていません、`DbType`または`Size`のプロパティ、`SAPParameter`します。 代わりに、ユーザーがの値を指定すると、`SAPParameter`値を内部的に確立されている .NET と SAP のデータ型マッピングに従って .NET データ型にキャストします。  
  
- SAP のデータ型のフィールド値の最大長`CURR`、 `DEC`、および`QUAN`は 29 桁です。 SAP では、31 の場所にこれらの値のデータ型をネイティブの .NET decimal データ型を変換先で 29 桁の制限が課せられます。  
  
- .NET データ型間のマッピング制限`Double`と SAP`FLTP`データ型に SAP システムから .NET 型にデータを読み取るときにオーバーフロー エラーが発生します。 .NET 型が正の 1.79769313486232 e 308 ~ SAP 負 1.79769313486232 e 308 から範囲の値を倍精度の 64 ビットの数値を表すことができますが`FLTP`で種類が解析され、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 1.8446744073709552E + 19; を超えることはできません有効な制限、`FLTP`型が負の 1.8446744073709552E + 正 1.8446744073709552E + 19 19 の範囲。  
  
- 基になるクライアント ライブラリで処理をタイムアウトに関する問題のため、[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]コマンドと接続のタイムアウトをサポートしていません。  
  
- [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]非同期コマンドの動作をサポートしていません。  
  
- SQL Server Integration Services (SSIS) プロジェクトで使用する場合、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] 8000 以上の文字の値を含む列のデータの取得に失敗します。 これに基づいて、SSIS の制限が原因です。  
  
  -   SSIS 変数に 4,000 文字よりも大きい値がサポートされていません。  
  
  -   4000 のワイド文字を超える値はサポートされていません。  
  
  -   1 バイト文字で 8000 を超える値はサポートされていません。  
  
## <a name="see-also"></a>参照  
 [.NET Framework Data Provider for mySAP Business Suite について](../../adapters-and-accelerators/adapter-sap/about-the-net-framework-data-provider-for-mysap-business-suite.md)