---
title: "マップを作成する場合は |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: maps, planning
ms.assetid: e86af976-b989-4e24-80d5-3a9a3ac4e443
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72dde6b09b7777204547d00d26af571c9998d73f
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="planning-to-create-maps"></a>マップ作成の計画
マップを使用して、あるスキーマに準拠している入力メッセージを別のスキーマに準拠している出力メッセージに変換します。 これらの変換は、簡単な場合と非常に複雑な場合があります。また、情報の計算や統合も行われます。  
  
 次の表は、マップの作成を計画するときに検討する必要がある項目を示しています。  
  
|計画段階の考慮事項|推奨|  
|-----------------------|--------------------|  
|どのマップを作成する必要があるか|Microsoft で処理するビジネス ドキュメントの一覧を作成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 この一覧には、注文書、請求書、出荷情報などが含まれます。 リスト含めることもこのような各ビジネス ドキュメントの 1 つ以上の別の取引先から受信する 1 つの取引先から受信した注文書の構造が発注書の構造と異なる場合など。<br /><br /> 一覧を参照し、異なる形式にするドキュメントまたは一般的な形式に変換して適切な処理を行うドキュメントを決定します。|  
|マップが必要な場所はどこか|送信ポート、受信ポート、およびビジネス プロセスを表すオーケストレーションでマップを使用できます。 ドキュメントを変換する場所を検討してください。|  
|変換する古いマップはあるか|[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] および [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 2009 で作成されたマップは、変更しないで移行できます。 移行されたマップは、十分な時間をかけてテストしてください。 ただし、古いバージョンの BizTalk で作成されたマップ開けない場合があります BizTalk Server でします。 **注:**より前のバージョンで作成されたマップ[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]が機能では正確に[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]または[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]2009 です。 ただし、マップが BizTalk Server で開けません可能性があります。 <br /><br /> 含むマップ**スクリプト**functoid またはカスタム functoid が追加作業が必要です。 詳細については、次を参照してください。 [Functoid の移行](../core/migrating-functoids.md)です。|  
  
## <a name="see-also"></a>参照  
 [マップの概要](../core/about-maps.md)   
 [Functoid の移行](../core/migrating-functoids.md)