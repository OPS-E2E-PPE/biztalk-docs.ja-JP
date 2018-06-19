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
# <a name="known-issues-with-edi-migration"></a><span data-ttu-id="600ce-102">EDI の移行に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="600ce-102">Known Issues with EDI Migration</span></span>
<span data-ttu-id="600ce-103">このトピックの EDI/HIPAA アダプタ モデルからの移行に関する既知の問題を説明します[!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)]BizTalk Server にします。</span><span class="sxs-lookup"><span data-stu-id="600ce-103">This topic describes known issues with migration from the EDI/HIPAA adapter model in [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] to BizTalk Server.</span></span>  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a><span data-ttu-id="600ce-104">FILE 送信ポート用の資格情報が移行されない</span><span class="sxs-lookup"><span data-stu-id="600ce-104">Credential Information Not Migrated for a FILE Send Port</span></span>  
 <span data-ttu-id="600ce-105">トランスポートの種類として FILE を使用して送信ポートを移行する場合、ホストにネットワーク共有へのアクセス権がないときにファイル フォルダーにアクセスするために使用する資格情報が移行されません。</span><span class="sxs-lookup"><span data-stu-id="600ce-105">When migrating a send port using the FILE transport type, the credentials used to access the file folder when the host does not have access to the network share will not be migrated.</span></span> <span data-ttu-id="600ce-106">移行後に、手動での資格情報を有効にして、ユーザー名とに、使用するパスワードを入力する必要があります、**認証**のページ、 **FILE トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="600ce-106">After migration, you will need to manually enable credentials, and enter the user name and password to be used, on the **Authentication** page of the **FILE Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="600ce-107">参照</span><span class="sxs-lookup"><span data-stu-id="600ce-107">See Also</span></span>  
 <span data-ttu-id="600ce-108">[EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="600ce-108">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 [<span data-ttu-id="600ce-109">EDI 移行ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="600ce-109">EDI Migration Utilities</span></span>](../core/edi-migration-utilities.md)