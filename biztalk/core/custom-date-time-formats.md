---
title: カスタムの日付/時刻形式 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5efbec4-3138-44d7-bc76-f9c21547e1d5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1496f1f506df06a4d5569c065cba3bf4f8cbdad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238474"
---
# <a name="custom-date-time-formats"></a>カスタムの日付/時刻書式

## <a name="overview"></a>概要
基になるファイルが古いために、フラット ファイル スキーマを作成するフラット ファイル形式で、ISO 8601 形式に準拠しない日付/時刻書式が使用される場合があります。 そのため、フラット ファイル スキーマを作成して、設定する、**データ型**のプロパティ、**フィールド要素**または**フィールド属性**XML スキーマ定義 (のいずれかのノードXSD) 言語プリミティブ データ型、 **xs:dateTime**、 **xs:time**、または**xs:date**、使用することができます、**カスタム日付/時刻書式**プロパティを別の形式の日付または時刻の値を指定します。  
  
> [!NOTE]
>  メッセージ ボックスに記憶域の時刻値を切り捨てます。 **xs:dateTime**と**xs:time**ミリ秒レベル下にある要素。 同様の精度の低下は、.NET の日付/時刻データ型に変換する場合にも発生します。  
  
 フラット ファイル逆アセンブラーは、このようなフィールドを対応する XML が変換されるときの値の書式、**カスタム日付/時刻書式**ISO 8601 準拠に変換するフラット ファイルの日付/時刻形式を許可するプロパティが使用されます等価です。 同様に、フラット ファイル アセンブラーでは、等価なフラット ファイルへの ISO 8601 準拠の日付/時刻値を変換、されるときに、書式指定文字列で指定、**カスタム日付/時刻書式**プロパティが使用されます、適切な日付を構築/フラット ファイルの予期される時刻形式。  
  
> [!NOTE]
>  既定では、XSD 日付/時刻データ型に対応する値は、複数ある形式のうち、ISO 8601 形式に準拠する必要があります。 として日付を表現する、簡単に言えば**YYYY MM DD**で表される時間と**hh:mm:ss** 24 時間表記を使用します。 日付と時刻の値が"T"文字で区切られた発生すると同時に、: **YYYY:MM:DDThh:mm:ss**です。  
  
 構成することができます、**カスタム日付/時刻書式**ユリウス暦を除くほとんどの日付と時刻の形式を持つプロパティです。 ドロップダウン リストにさまざまな選択肢が用意されていますが、別の書式を入力して選択することもできます。 日付と時刻の形式は、共通言語ランタイム (CLR) を使用して**DateTime**機能します。 例外的に、d、m または M が 1 文字だけの場合は、前に自動的にパーセント記号 (%) が付加され、DataTime 値の対応する要素の 1 つが生成されます。 カスタム日付/時刻書式で使用できる区切り記号は、ダッシュ (-)、スラッシュ (/) およびピリオド (.) です。 詳細については**DateTime**形式が Visual Studio ドキュメント コレクション内で検索 datetimeformatinfo」を参照します。  
  
## <a name="see-also"></a>参照  
-  [フィールドに関する考慮事項](../core/field-considerations.md)   
-  **データ型 (すべてのスキーマのノード プロパティ)** と**カスタム日時書式指定 (フラット ファイル スキーマのノード プロパティ)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]