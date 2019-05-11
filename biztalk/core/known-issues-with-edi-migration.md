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
# <a name="known-issues-with-edi-migration"></a><span data-ttu-id="c4372-102">EDI の移行に関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="c4372-102">Known Issues with EDI Migration</span></span>
<span data-ttu-id="c4372-103">このトピックでは、EDI/HIPAA アダプタ モデルからの移行に関する既知の問題を説明します。 [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] BizTalk Server にします。</span><span class="sxs-lookup"><span data-stu-id="c4372-103">This topic describes known issues with migration from the EDI/HIPAA adapter model in [!INCLUDE[btsBizTalkServer2006](../includes/btsbiztalkserver2006-md.md)] to BizTalk Server.</span></span>  
  
## <a name="credential-information-not-migrated-for-a-file-send-port"></a><span data-ttu-id="c4372-104">ファイル送信ポートの資格情報が移行されません。</span><span class="sxs-lookup"><span data-stu-id="c4372-104">Credential Information Not Migrated for a FILE Send Port</span></span>  
 <span data-ttu-id="c4372-105">ファイル トランスポートの種類を使用して送信ポートを移行するときに、ホストにネットワーク共有へのアクセスがあるない場合にファイル フォルダーにアクセスするために使用する資格情報は移行されません。</span><span class="sxs-lookup"><span data-stu-id="c4372-105">When migrating a send port using the FILE transport type, the credentials used to access the file folder when the host does not have access to the network share will not be migrated.</span></span> <span data-ttu-id="c4372-106">移行後に、手動での資格情報を有効にして、ユーザー名とで、使用するパスワードを入力する必要があります、**認証**のページ、 **FILE トランスポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="c4372-106">After migration, you will need to manually enable credentials, and enter the user name and password to be used, on the **Authentication** page of the **FILE Transport Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4372-107">参照</span><span class="sxs-lookup"><span data-stu-id="c4372-107">See Also</span></span>  
 <span data-ttu-id="c4372-108">[EDI および AS2 ソリューションのトラブルシューティング](../core/troubleshooting-edi-and-as2-solutions.md) </span><span class="sxs-lookup"><span data-stu-id="c4372-108">[Troubleshooting EDI and AS2 Solutions](../core/troubleshooting-edi-and-as2-solutions.md) </span></span>  
 [<span data-ttu-id="c4372-109">EDI 移行ユーティリティ</span><span class="sxs-lookup"><span data-stu-id="c4372-109">EDI Migration Utilities</span></span>](../core/edi-migration-utilities.md)