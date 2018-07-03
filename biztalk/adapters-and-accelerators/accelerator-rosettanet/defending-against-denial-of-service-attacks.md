---
title: サービス拒否攻撃に対する防御 |Microsoft Docs
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
ms.openlocfilehash: ab2aa48e126aafc7b2202547fd72806b5d471ef4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976939"
---
# <a name="defending-against-denial-of-service-attacks"></a><span data-ttu-id="9f16d-102">サービス拒否攻撃から保護</span><span class="sxs-lookup"><span data-stu-id="9f16d-102">Defending Against Denial-of-Service Attacks</span></span>
<span data-ttu-id="9f16d-103">サービス拒否攻撃は Microsoft® のインストールを開始ユーザーでした[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]によって生じて、RNIFReceive.aspx ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9f16d-103">Someone could start a denial-of-service attack against an installation of Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] by stressing the RNIFReceive.aspx receive page.</span></span> <span data-ttu-id="9f16d-104">そのページに多数の空のメッセージを送信する場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f16d-104">They could do so by sending large numbers of empty messages to that page.</span></span> <span data-ttu-id="9f16d-105">このような攻撃を放置すると、ASPX 受信ページで発行されたイベントがイベント ログに収まりきらなくなる場合があります。</span><span class="sxs-lookup"><span data-stu-id="9f16d-105">If left unchecked, such an attack could flood the event log with events published by the ASPX receive page.</span></span>  
  
## <a name="defending-against-an-attack"></a><span data-ttu-id="9f16d-106">攻撃からの保護</span><span class="sxs-lookup"><span data-stu-id="9f16d-106">Defending Against an Attack</span></span>  
 <span data-ttu-id="9f16d-107">サービス拒否攻撃からサーバーを守るには、イベント ログを適度なサイズに維持し、また大量のイベント数を処理する手段をとることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9f16d-107">To defend your server against denial-of-service attacks, it is recommended that you maintain the event log at a reasonable size and take steps to deal with excessive numbers of events.</span></span> <span data-ttu-id="9f16d-108">たとえば、最大ログ サイズを設定する、イベントの上書きが可能な手段をとる、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) を使用してログのサイズを管理するなどの方法があります。</span><span class="sxs-lookup"><span data-stu-id="9f16d-108">You can accomplish this by setting the maximum log size, selecting a way of overwriting events, or using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) to manage the size of the log.</span></span> <span data-ttu-id="9f16d-109">詳細については、Microsoft のヘルプを参照してください。 [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™ します。</span><span class="sxs-lookup"><span data-stu-id="9f16d-109">For more information, see Help for Microsoft [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f16d-110">参照</span><span class="sxs-lookup"><span data-stu-id="9f16d-110">See Also</span></span>  
 [<span data-ttu-id="9f16d-111">構成、証明書、データベース、セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="9f16d-111">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)