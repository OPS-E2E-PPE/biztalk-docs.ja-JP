---
title: BizTalk Server で SWIFT エラー コード |Microsoft Docs
description: BizTalk Server で、SWIFT アクセラレータ クラスと検証の種類を表示します。
ms.custom: ''
ms.date: 08/16/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03699986-965b-4a28-ab2e-09f110fb4db6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eeefb9fc918893b8caaab6852d77a417cab340e3
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529788"
---
# <a name="swift-error-codes"></a>SWIFT エラー コード
SWIFT では、財務 (FIN) メッセージのセットに対して多くのネットワークによる検証を定義します。 各検証は、メッセージの内容に対してチェックの種類に関連していて、3 文字のエラー コードに関連付けられました。 エラー コードの最初の文字は、検出された問題のクラスのことを意味する、文字です。 残りの 2 つの文字 (クラスと組み合わせた) ときにエラーの詳細を示すためし、常に 2 桁のコードとして表示されます。  

## <a name="class-of-errors"></a>エラーのクラス  
 次の表は、ドライブの文字、検証の種類、エラーの各クラスに関連付けられているルールの変更とエラーのクラスがサポートされているかどうか。  
  
|クラス|検証の種類とルールの変更|サポートされていますか。|  
|-----------|-------------------------------------|----------------|  
|**C、D、E**|セマンティック検証規則は、0-299|Supported|  
|**Knn**|フィールドに無効なコード word *nn*|Supported|  
|**M50**|メッセージの長さを超えています|サポートされていない|  
|**M60**|見つかった非 SWIFT 文字|Supported|  
|**T**|テキスト検証のエラー コード|Supported|  
|**G**|メッセージのユーザー グループ (マグカップ) Textval 規則の特定のエラー コード|サポートされていない|  
|**B**|付加価値サービスの特殊なエラー コード|サポートされていない|  
  
 SWIFT のすべてのエラーを参照する必要があります、 *SWIFT ユーザー向けハンドブック*します。 詳細については、および SWIFT エラー コードの完全な一覧についてを参照してください。、*メッセージ形式の検証規則*のボリューム、 *SWIFT ユーザー向けハンドブック*します。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] このパブリケーションの 2003 年 9 月のエディションで、規則を実装します。 SWIFT Web サイトにアクセスすることができます[ http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)します。  

## <a name="validation-errors"></a>検証エラー  
 A4SWIFT で定義されているいくつかのコードがあります。 これらのエラー コードは、検証/ネットワーク ルールを作成し、このような規則の SWIFT で定義されている、対応するエラー コードがない、A4SWIFT、によって実装されるで使用されます。 次の表は、エラー コードとエラーがスローされた対応するケースを示しています。 エラーをスローする特定のフィールドです。  
  
|エラー コード|説明|  
|----------------|-----------------|  
|A4SWIFT001|複数行のフィールドの最初の文字にすることはできません ':' または '-' 行目以降の文字。|  
|A4SWIFT002|フィールドには、無効な値が含まれています。|  
  
> [!NOTE]
>  [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 内部アプリケーションがメッセージを使用しているために、一部の従来のメッセージのサポートが含まれます。 したがって、A4SWIFT は、関連付けられている SWIFT ルールおよびエラー コードを保持します。

## <a name="more-good-info"></a>詳細な情報
[トラブルシューティング: 問題と解決方法](troubleshooting-issues-and-resolutions1.md)  
[既知の問題](known-issues5.md)  
[一般的な用語と定義](glossary6.md)