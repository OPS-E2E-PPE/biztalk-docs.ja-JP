---
title: サービス拒否攻撃から保護 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, denial-of-service attacks
- denial-of-service attacks
ms.assetid: 63342d7a-a5df-4e11-9037-93175d8f7ea7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 667b9d321f7703f770297b001ef2a99be2bf4902
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209706"
---
# <a name="defending-against-denial-of-service-attacks"></a><span data-ttu-id="35074-102">サービス拒否攻撃から保護</span><span class="sxs-lookup"><span data-stu-id="35074-102">Defending Against Denial-of-Service Attacks</span></span>
<span data-ttu-id="35074-103">他のユーザーのインストールに対するサービス拒否攻撃を開始できませんでした[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]によって生じて、RNIFReceive.aspx ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="35074-103">Someone could start a denial-of-service attack against an installation of [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] by stressing the RNIFReceive.aspx receive page.</span></span> <span data-ttu-id="35074-104">そのページに多数の空のメッセージを送信するときは可能性があります。</span><span class="sxs-lookup"><span data-stu-id="35074-104">They could do so by sending large numbers of empty messages to that page.</span></span> <span data-ttu-id="35074-105">このような攻撃を放置すると、ASPX 受信ページで発行されたイベントがイベント ログに収まりきらなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="35074-105">If left unchecked, such an attack could flood the event log with events published by the ASPX receive page.</span></span>  
  
## <a name="defending-against-an-attack"></a><span data-ttu-id="35074-106">攻撃からの保護</span><span class="sxs-lookup"><span data-stu-id="35074-106">Defending Against an Attack</span></span>  
 <span data-ttu-id="35074-107">サービス拒否攻撃からサーバーを守るには、イベント ログを適度なサイズに維持し、また大量のイベント数を処理する手段をとることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="35074-107">To defend your server against denial-of-service attacks, it is recommended that you maintain the event log at a reasonable size and take steps to deal with excessive numbers of events.</span></span> <span data-ttu-id="35074-108">たとえば、最大ログ サイズを設定する、イベントの上書きが可能な手段をとる、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) を使用してログのサイズを管理するなどの方法があります。</span><span class="sxs-lookup"><span data-stu-id="35074-108">You can accomplish this by setting the maximum log size, selecting a way of overwriting events, or using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) to manage the size of the log.</span></span> <span data-ttu-id="35074-109">詳細については、ヘルプを参照して[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™ します。</span><span class="sxs-lookup"><span data-stu-id="35074-109">For more information, see Help for [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35074-110">参照</span><span class="sxs-lookup"><span data-stu-id="35074-110">See Also</span></span>  
 [<span data-ttu-id="35074-111">構成、証明書、データベース、およびセキュリティを管理します。</span><span class="sxs-lookup"><span data-stu-id="35074-111">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)