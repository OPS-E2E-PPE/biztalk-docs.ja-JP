---
title: "BizTalk ログの配布を他のデータベースの構成 |Microsoft ドキュメント"
description: "BizTalk Server のバックアップ ジョブ、および BizTalk Server でのログ配布にカスタム データベースを追加します。"
ms.custom: 
ms.date: 11/01/2017
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
ms.openlocfilehash: 1f4eb0b690f81b16d739183633c6507b2ad87226
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="configuring-biztalk-server-log-shipping-for-additional-databases"></a>BizTalk Server に対してログ配布を他のデータベースを構成します。

## <a name="overview"></a>概要
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、BizTalk Server のバックアップ ジョブに追加するジョブは自動的に追加[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ログ配布します。 BizTalk Server のバックアップ ジョブに追加される新しいデータベースのログ配布を構成する追加の手順を実行する必要はありません。 ただし、下にある適切なカスタム データベースを追加するようにして、 \<OtherDatabases > SampleUpdateInfo.xml ファイルのセクションです。 [ログ配布の送信先システムを構成する](../core/how-to-configure-the-destination-system-for-log-shipping.md)と[カスタム データベースを戻す](../core/how-to-back-up-custom-databases.md)のガイダンスを紹介します。
  
## <a name="see-also"></a>参照  
 [BizTalk Server のログ配布の構成](../technical-guides/configuring-biztalk-server-log-shipping.md)