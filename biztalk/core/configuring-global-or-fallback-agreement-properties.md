---
title: グローバルまたはフォールバック アグリーメント プロパティの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c375d03-6f22-4a67-9eac-d8896de2f7ee
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0eb693a17cad17eadaf0d005d12075dde30daa33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233210"
---
# <a name="configuring-global-or-fallback-agreement-properties"></a>グローバルまたはフォールバック アグリーメントのプロパティの構成
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、インターチェンジの解決に使用するためのアグリーメントが見つからない場合、フォールバック アグリーメント プロパティを使用してメッセージを処理します。 フォールバック アグリーメント プロパティは、アグリーメントがわかっているときは使用されず、すべてのアグリーメントに適用されるものではありません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はメッセージを受信すると、アグリーメントの送信者の情報とメッセージの送信者の情報を照合しようと試みます。 送信者の情報は、X12 メッセージの場合は IS5 および IS6 データ要素に格納され、EDIFACT の場合は UNB2.1 および UNB 2.2 データ要素に格納されています。 契約情報は、の一方向アグリーメント タブにある識別子タブには、**アグリーメントのプロパティ** ダイアログ ボックス。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がアグリーメントを見つけられない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はフォールバック アグリーメント プロパティを使用して名前空間を決定し、メッセージを処理して、受信確認を送信します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がメッセージを送信するとき、EDI 送信パイプラインが、メッセージ ボックスの XML メッセージをサブスクライブしている送信ポートとアグリーメントに関連付けられている送信ポートを照合することにより、メッセージの解決に使用するアグリーメントを特定します。 送信ポートがアグリーメントに関連付けられていない場合、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] はフォールバック アグリーメント プロパティを使用して、メッセージを送信するために処理します。  
  
> [!NOTE]
>  送信ポートの関連付けは、アグリーメントを解決する 1 つの方法にすぎません。 送信メッセージのアグリーメントの解決の詳細については、次を参照してください。[アグリーメントの解決と送信 EDI メッセージのスキーマの決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [設定の X12 フォールバック アグリーメントのプロパティ](../core/configuring-x12-fallback-agreement-properties.md)  
  
-   [EDIFACT フォールバック アグリーメント プロパティの構成](../core/configuring-edifact-fallback-agreement-properties.md)  
  
## <a name="see-also"></a>参照  
 [EDI 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-edi-processing.md)