---
title: グローバルまたはフォールバック アグリーメント プロパティの構成 |Microsoft Docs
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
ms.openlocfilehash: d44624a4f505cf7d3c4e53fe55e4203917cf41f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391081"
---
# <a name="configuring-global-or-fallback-agreement-properties"></a>グローバルまたはフォールバック アグリーメントのプロパティの構成
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] インターチェンジに解決するためのアグリーメントは検出されないときにメッセージを処理するのにには、フォールバック アグリーメントのプロパティを使用します。 フォールバック アグリーメントのプロパティはアグリーメントがわかっている場合は使用されませんし、すべてのアグリーメントには適用されません。  
  
 ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]がメッセージを受信メッセージの送信者の情報と、アグリーメントの送信者の情報と一致させようとします。 送信者の情報は、X12 の ISA5 および ISA6 のデータ要素では、メッセージと EDIFACT の場合は UNB2.1 および UNB 2.2 データ要素です。 契約の情報は、の一方向アグリーメント タブで、識別子 タブは、**アグリーメントのプロパティ** ダイアログ ボックス。 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、契約書を検出しません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]フォールバック アグリーメント プロパティを使用して名前空間を決定し、メッセージを処理し、受信確認を送信します。  
  
 ときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アグリーメントに関連付けられている送信ポートと送信を照合することによってポートにメッセージが解決されるアグリーメントが、メッセージ ボックス内の XML メッセージにサブスクライブ メッセージを送信し、EDI 送信パイプラインを決定します。 送信ポートは、アグリーメントに関連付けられていない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]を送信するためのメッセージを処理するフォールバック アグリーメントのプロパティを使用します。  
  
> [!NOTE]
>  送信ポートの関連付けはアグリーメントの解決を行う方法の 1 つのみです。 送信メッセージのアグリーメントの解決の詳細については、次を参照してください。[アグリーメントの解決と送信 EDI メッセージのスキーマ決定](../core/agreement-resolution-and-schema-determination-for-outgoing-edi-messages.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [X12 フォールバック アグリーメントのプロパティの構成](../core/configuring-x12-fallback-agreement-properties.md)  
  
-   [EDIFACT フォールバック アグリーメントのプロパティの構成](../core/configuring-edifact-fallback-agreement-properties.md)  
  
## <a name="see-also"></a>参照  
 [EDI 処理におけるアグリーメントのロール](../core/the-role-of-agreements-in-edi-processing.md)