---
title: EDI の移行に関する既知の問題 |Microsoft ドキュメント
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
ms.openlocfilehash: bd62c1c965e814929537a62dc5d49be7e017ae3b
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005971"
---
# <a name="known-issues-with-edi-migration"></a>EDI の移行に関する既知の問題
このトピックの EDI/HIPAA アダプタ モデルからの移行に関する既知の問題を説明します[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]BizTalk Server にします。  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a>FILE 送信ポート用の資格情報が移行されない  
 トランスポートの種類として FILE を使用して送信ポートを移行する場合、ホストにネットワーク共有へのアクセス権がないときにファイル フォルダーにアクセスするために使用する資格情報が移行されません。 移行後に、手動での資格情報を有効にして、ユーザー名とに、使用するパスワードを入力する必要があります、**認証**のページ、 **FILE トランスポートのプロパティ** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md)   
 [EDI 移行ユーティリティ](../core/edi-migration-utilities.md)