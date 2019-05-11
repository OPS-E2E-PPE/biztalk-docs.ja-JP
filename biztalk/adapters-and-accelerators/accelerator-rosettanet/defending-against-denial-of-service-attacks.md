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
ms.openlocfilehash: f0dc316f039e56271f4d5540e3853aa82287b20d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283995"
---
# <a name="defending-against-denial-of-service-attacks"></a><span data-ttu-id="cd0bf-102">サービス拒否攻撃から保護</span><span class="sxs-lookup"><span data-stu-id="cd0bf-102">Defending Against Denial-of-Service Attacks</span></span>
<span data-ttu-id="cd0bf-103">サービス拒否攻撃は Microsoft® のインストールを開始ユーザーでした[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]によって生じて、RNIFReceive.aspx ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd0bf-103">Someone could start a denial-of-service attack against an installation of Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] by stressing the RNIFReceive.aspx receive page.</span></span> <span data-ttu-id="cd0bf-104">そのページに多数の空のメッセージを送信する場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd0bf-104">They could do so by sending large numbers of empty messages to that page.</span></span> <span data-ttu-id="cd0bf-105">場合はオフの場合、このような攻撃は、ASPX によって発行されたイベントをイベント ログをあふれでした左には、ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd0bf-105">If left unchecked, such an attack could flood the event log with events published by the ASPX receive page.</span></span>  
  
## <a name="defending-against-an-attack"></a><span data-ttu-id="cd0bf-106">攻撃からの保護</span><span class="sxs-lookup"><span data-stu-id="cd0bf-106">Defending Against an Attack</span></span>  
 <span data-ttu-id="cd0bf-107">サーバーに対するサービス拒否攻撃を防御するために、適切なサイズのイベント ログを維持し、過度のイベントを処理する手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cd0bf-107">To defend your server against denial-of-service attacks, it is recommended that you maintain the event log at a reasonable size and take steps to deal with excessive numbers of events.</span></span> <span data-ttu-id="cd0bf-108">これには、最大ログ サイズを設定して、イベントを上書きするかを使用する方法を選択する[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® ログのサイズを管理する Management Instrumentation (WMI)。</span><span class="sxs-lookup"><span data-stu-id="cd0bf-108">You can accomplish this by setting the maximum log size, selecting a way of overwriting events, or using [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]® Management Instrumentation (WMI) to manage the size of the log.</span></span> <span data-ttu-id="cd0bf-109">詳細については、Microsoft のヘルプを参照してください。 [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™ します。</span><span class="sxs-lookup"><span data-stu-id="cd0bf-109">For more information, see Help for Microsoft [!INCLUDE[btsWinSvrNoVersion](../../includes/btswinsvrnoversion-md.md)]™.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd0bf-110">参照</span><span class="sxs-lookup"><span data-stu-id="cd0bf-110">See Also</span></span>  
 [<span data-ttu-id="cd0bf-111">構成、証明書、データベース、セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="cd0bf-111">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)