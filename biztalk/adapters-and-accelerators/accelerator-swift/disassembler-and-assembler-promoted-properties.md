---
title: "昇格させたプロパティの逆アセンブラおよびアセンブラ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, promoted properties
- promoted properties, assembler
- promoted properties, disassembler
- assembler, promoted properties
ms.assetid: 342b0250-bdf7-45ce-8964-3aeda89989b1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab1e0cab902ded34f10cf03bc6e8229d28123be2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="disassembler-and-assembler-promoted-properties"></a>昇格させたプロパティの逆アセンブラおよびアセンブラ
逆アセンブラーまたはアセンブラーのプロパティは 2 つのカテゴリに分類されますルーティングとフィルタ リングのためのルーティング プロパティ。内部処理用のランタイム プロパティ。  
  
このトピックでは、追加、およびメッセージ ボックス データベースに SWIFT 逆アセンブラーによって公開されるすべてのメッセージの昇格されるプロパティの一覧を示します。  
  
## <a name="routing-properties"></a>ルーティング プロパティ

SWIFT の逆アセンブラーは、ルーティングのプロパティを昇格させます。 コンテンツ ベースのルーティング (送信ポート フィルター) これらのプロパティを使用し、オーケストレーションでのフィルタ リングを受信できます。  
  
|昇格の名前|Description|データ型|値の範囲|使用例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_BatchId**|SWIFT の逆アセンブラーが受信バッチの処理時に動的に生成されたグローバルに一意の識別子です。 逆アセンブラーは、同じバッチから送信されたメッセージ ボックス データベースに公開されたすべてのメッセージにこのバッチ識別子を割り当てます。<br /><br /> 設定**-1**の 1 つのメッセージ (受信のバッチからは発信されません)。|文字列|「-1」または*グローバル一意識別子 (GUID)*|同じメッセージを関連付けるため**A4SWIFT_BatchId**受信した最初を同じバッチにグループ化する値。|  
|**A4SWIFT_BreValidationErrors**|ビジネス ルール エンジン (BRE) の検証中に発生した検証エラーの数を示します。|数値|>= 0|BRE の検証は失敗しなかったメッセージのフィルター (**A4SWIFT_BREValidationErrors**が 0 に等しい)。|  
|**A4SWIFT_Failed**|メッセージ (解析と検証) を処理中に障害が発生したかどうかを示します。 設定**True**場合**A4SWIFT_ParseErrors** + **A4SWIFT_XmlValidationErrors** + **A4SWIFT_BreValidationErrors** > 0 です。|ブール値|True、False|唯一の有効な SWIFT メッセージのフィルター (**A4SWIFT_Failed** equals **False**)。|  
|**A4SWIFT_ParseErrors**|解析中に発生した解析エラーの数を示します。|数値|>= 0|解析は失敗しなかったメッセージのフィルター (**A4SWIFT_ParseErrors**が 0 に等しい)。|  
|**A4SWIFT_PosInBatch**|受信バッチから発信されるメッセージの序数位置を示します。 含むバッチの *n* メッセージ、 **A4SWIFT_PosInBatch**は 1 から値を受け取って *n*メッセージの序数に対応する、バッチに配置します。<br /><br /> 設定**0**メッセージがバッチ ヘッダーである場合。<br /><br /> 設定**n+1**メッセージがバッチ トレーラーである場合。<br /><br /> 設定**1**場合は、メッセージ自体はバッチ全体 (バッチの断片化が無効になっています)。<br /><br /> 設定**-1**の 1 つのメッセージ (受信のバッチからは発信されません)。|数値|>= -1|同じ受信バッチからのメッセージを受信した元の順序に並べ替えます。|  
|**A4SWIFT_XmlValidationErrors**|XML の検証中に発生した検証エラーの数を示します。|数値|>= 0|XML 検証は失敗しなかったメッセージのフィルター (**A4SWIFT_XmlValidationErrors**が 0 に等しい)。|  
  
> [!NOTE]
>  一般に、すべてのルーティングやフィルター式を評価する必要があります**A4SWIFT_Failed**ルーティングで他のプロパティを評価する前にします。 のみ**A4SWIFT_Failed**を昇格して利用できることが保証されます。 残りのプロパティは、有効な単一メッセージ (非バッチ メッセージ)、メッセージ ボックス データベースに公開をご利用いただけません。 その他のプロパティは昇格のみ*失敗*単一メッセージおよびバッチのメッセージの有効な (失敗)。  

## <a name="runtime-properties"></a>ランタイム プロパティ

SWIFT の逆アセンブラーは、ランタイム プロパティを昇格し、内部プロセスの実行時にそれらを使用します。 昇格させたとコンテキストに応じて、いくつかの条件でルーティングに使用可能なのみされます。 一般に、このプロパティを使用しないルーティングまたは動的フィルタの。 昇格させたして利用できる、保証はありません。 一部のシナリオで取得するか、ルーティング プロパティを使用してフィルター処理した後、これらのプロパティを検査できます。 次の表は、ランタイム プロパティを一覧表示します。  
  
|昇格の名前|Description|データ型|値の範囲|使用例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_IsMessageHeaderValued**|マルチパート メッセージのヘッダー部にデータが存在するかどうかを示します。 設定**True**ヘッダー部分には、データ (バッチから受信したメッセージのエンベロープ ヘッダーをメッセージ) が含まれている場合。 設定**False**ヘッダー部分が空の場合。|ブール値|True、False|(たとえば、メッセージの修復オーケストレーション) で取得したメッセージのヘッダー部分を検査するかどうかを決定します。|  
|**A4SWIFT_IsMessageTrailerValued**|マルチパート メッセージのトレーラー部にデータが存在するかどうかを示します。 設定**True**トレーラー部にデータ (バッチから受信したメッセージのエンベロープ トレーラーをメッセージ) が含まれている場合。 設定**False**トレーラー部が空の場合。|ブール値|True、False|(たとえば、メッセージの修復オーケストレーション) で取得したメッセージのトレーラー部を検査するかどうかを決定します。|  
|**A4SWIFT_MessageType**|3 桁の数値を示す、SWIFT SWIFT ヘッダー メッセージの種類 (**MT*xxx** *)。|文字列|*3 桁の数字*|動的に SWIFT メッセージ、メッセージの種類を識別します。|  
|**A4SWIFT_MessageType2**|3 桁の数値を示す、SWIFT SWIFT ヘッダー メッセージの種類 (**MT*xxx** *)。 使用する場合にのみ**A4SWIFT_MessageType** SWIFT ヘッダーが見つかりません。|文字列|*3 桁の数字*|動的に SWIFT メッセージ、メッセージの種類を識別します。|  
|**A4SWIFT_NumberOfParts**|マルチパート メッセージの部分の数を示します。<br /><br /> 設定**1**だけの場合、ボディ部 (バッチ、またはバッチ ヘッダーまたはバッチのエンベロープからバッチ トレーラーに由来いない、有効な個々 SWIFT メッセージを含む)。<br /><br /> 設定**2**かどうか本文とエラーの部分に (本文の一部が失敗したメッセージまたはエラーの部分に XML エラーのコレクションを含むバッチを含む) が存在します。<br /><br /> 設定**3**本体、ヘッダー、およびトレーラーの部分に使用し、一部を含むメッセージをトレーラ場合、ヘッダー部分を含むメッセージ エンベロープのヘッダー、バッチから送信された、有効な個々 SWIFT メッセージを含む (本文部分が存在かどうかエンベロープのトレーラーを使用する場合: **A4SWIFT_IsMessageHeaderValued**と**A4SWIFT_IsMessageTrailerValued**ヘッダーおよびトレーラの部分にデータが存在するかどうか)。|数値|1, 2, 3|メッセージ部分の指定した数をフィルター (たとえば、抽出**A4SWIFT_NumberOfParts**等しい 2 つのメッセージ修復オーケストレーションの受信図形)。|  
|**A4SWIFT_SecondaryMessageType**|文字列値を示す、SWIFT SWIFT ヘッダーでメッセージのサブタイプ (**MT*xxx_XYZ** *)。|文字列|*任意の文字列*|メッセージの SWIFT メッセージのサブタイプを動的に識別します。|  
  
 
## <a name="see-also"></a>参照  
[A4SWIFT_ * 昇格させたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   