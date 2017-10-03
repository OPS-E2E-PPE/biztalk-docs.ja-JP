---
title: "BizTalk Server での迅速なエラー コード |Microsoft ドキュメント"
description: "BizTalk Server に SWIFT アクセラレータのクラスと検証の種類を表示します。"
ms.custom: 
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03699986-965b-4a28-ab2e-09f110fb4db6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6d8e027eb9cce1cf66342484070310141e10b5d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="swift-error-codes"></a>SWIFT エラー コード
SWIFT では、財務 (FIN) メッセージのセットに対して多くのネットワークによる検証を定義します。 各検証は、メッセージの内容に対してチェックの種類に関連して、3 文字のエラー コードに関連付けられてです。 エラー コードの最初の文字は、クラス、検出された問題のことを意味し、文字です。 残りの 2 つの文字は、(クラスと組み合わせて) 場合、エラーの詳細を示すためし、常に 2 桁のコードとして表示されます。  

## <a name="class-of-errors"></a>エラーのクラス  
 次の表は、ドライブの文字、検証の種類、ルールの変更が、エラーの各クラスに関連付けられているエラーのクラスがサポートされているかどうかとします。  
  
|クラス|検証の種類および規則の変更|サポートされているか。|  
|-----------|-------------------------------------|----------------|  
|**C、D、E**|セマンティック検証規則は、0-299|Supported|  
|**Knn**|フィールドに無効なコード ワード*nn*|Supported|  
|**M50**|メッセージの長さを超えています|サポートされていない|  
|**M60**|見つかった非 SWIFT 文字|Supported|  
|**T**|テキスト検証のエラー コード|Supported|  
|**G**|メッセージのユーザー グループ (の入ったマグ) Textval 規則の特定のエラー コード|サポートされていない|  
|**B**|付加価値サービスの特殊なエラー コード|サポートされていない|  
  
 SWIFT のすべてのエラーを参照してください、 *SWIFT ユーザー マニュアル*です。 詳細については、迅速なエラー コードの完全な一覧についてを参照してください、*メッセージ形式の検証規則*のボリューム、 *SWIFT ユーザー マニュアル*です。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]このパブリケーションの 2003 年 9 月のエディションで、規則を実装します。 SWIFT Web サイトにアクセスすることができます[http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)です。  

## <a name="validation-errors"></a>検証エラー  
 A4SWIFT で定義されている一部のコードがあります。 これらのエラー コードが作成され、このようなルールの SWIFT によって定義された対応するエラー コードがないように A4SWIFT、によって実装される検証/ネットワーク ルールで使用されます。 次の表は、エラー コードと、エラーがスローされた、対応するケースを示しています。 エラーをスローする特定のフィールドです。  
  
|エラー コード|Description|  
|----------------|-----------------|  
|A4SWIFT001|複数行のフィールドの最初の文字にすることはできません ':' または '-' 行目以降の文字です。|  
|A4SWIFT002|フィールドには、無効な値が含まれています。|  
  
> [!NOTE]
>  [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]内部アプリケーションがこれらのメッセージを使用するため、一部のレガシ メッセージのサポートが含まれます。 したがって、A4SWIFT は、関連付けられている SWIFT ルールおよびエラー コードを保持します。

## <a name="more-good-info"></a>詳細な情報
[トラブルシューティング: 問題と解決策](troubleshooting-issues-and-resolutions1.md)  
[既知の問題](known-issues5.md)  
[一般的な用語と定義](glossary6.md)