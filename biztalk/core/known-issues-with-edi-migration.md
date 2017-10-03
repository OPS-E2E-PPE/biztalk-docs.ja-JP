---
title: "EDI の移行に関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc5d0a7e-974d-4e3b-a406-412420779456
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b642c56151750232be3d17aa3f3cb3b8c858474c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-migration"></a>EDI の移行に関する既知の問題
このトピックでは、[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] の EDI/HIPAA アダプター モデルから [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] への移行に関する既知の問題について説明します。  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a>FILE 送信ポート用の資格情報が移行されない  
 トランスポートの種類として FILE を使用して送信ポートを移行する場合、ホストにネットワーク共有へのアクセス権がないときにファイル フォルダーにアクセスするために使用する資格情報が移行されません。 移行後に、手動での資格情報を有効にして、ユーザー名とに、使用するパスワードを入力する必要があります、**認証**のページ、 **FILE トランスポートのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)   
 [EDI 移行ユーティリティ](../core/edi-migration-utilities.md)