---
title: "BizTalk Server に対してログ配布を他のデータベースの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fc2ae67-5cb9-4d53-9bf7-c88f84914960
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b16b1d262b07ecaa62e87456f10bece225b3b34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a>BizTalk Server に対してログ配布を他のデータベースを構成します。
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、BizTalk Server のバックアップ ジョブに追加するジョブは自動的に追加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布します。 BizTalk Server のバックアップ ジョブに追加される新しいデータベースのログ配布を構成する追加の手順を実行する必要はありません。 ただし、下にある適切なカスタム データベースを追加するようにして、 \<OtherDatabases > セクションの手順 22 の説明に従って、SampleUpdateInfo.xml ファイルの[ログ配布用に送信先システムを構成する方法](http://go.microsoft.com/fwlink/?LinkId=151402)(http://go.microsoft.com/fwlink/しますか?LinkId = 151402) で[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ヘルプします。  
  
## <a name="see-also"></a>参照  
 [ログ配布の BizTalk Server の構成](../technical-guides/configuring-biztalk-server-log-shipping.md)