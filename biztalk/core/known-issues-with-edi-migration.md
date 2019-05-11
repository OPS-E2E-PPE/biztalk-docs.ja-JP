---
title: EDI の移行に関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc5d0a7e-974d-4e3b-a406-412420779456
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 480a448691072ec46a2cff1dad8f114ef3e35691
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380756"
---
# <a name="known-issues-with-edi-migration"></a>EDI の移行に関する既知の問題
このトピックでは、EDI/HIPAA アダプタ モデルからの移行に関する既知の問題を説明します。 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] BizTalk Server にします。  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a>ファイル送信ポートの資格情報が移行されません。  
 ファイル トランスポートの種類を使用して送信ポートを移行するときに、ホストにネットワーク共有へのアクセスがあるない場合にファイル フォルダーにアクセスするために使用する資格情報は移行されません。 移行後に、手動での資格情報を有効にして、ユーザー名とで、使用するパスワードを入力する必要があります、**認証**のページ、 **FILE トランスポートのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)   
 [EDI 移行ユーティリティ](../core/edi-migration-utilities.md)