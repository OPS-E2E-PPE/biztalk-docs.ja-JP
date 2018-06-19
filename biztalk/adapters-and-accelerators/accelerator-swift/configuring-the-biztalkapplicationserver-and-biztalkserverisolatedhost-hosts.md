---
title: BizTalkApplicationServer と BizTalkServerIsolatedHost ホストの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, hosts
- BizTalkApplicationServer host
- hosts
- BizTalkServerIsolatedHost host
ms.assetid: 17bc9f01-ff87-427d-8411-6a065814ba1e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8459debcd52ce990bc98adf3a2a2372206bae336
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208802"
---
# <a name="configuring-the-biztalkapplicationserver-and-biztalkserverisolatedhost-hosts"></a><span data-ttu-id="79477-102">BizTalkApplicationServer と BizTalkServerIsolatedHost ホストの構成</span><span class="sxs-lookup"><span data-stu-id="79477-102">Configuring the BizTalkApplicationServer and BizTalkServerIsolatedHost Hosts</span></span>
<span data-ttu-id="79477-103">BizTalk メッセージのサーバーには、メッセージング (送信および受信メッセージ) を制限するためには、MSMQT の送信を実行するいると、受信ハンドラー, メッセージング サーバー上でのみ実行する既定のホストを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="79477-103">To limit the messaging (sending and receiving messages) to the BizTalk Messaging servers, you need to configure the default hosts, which are running the MSMQT send and receive handlers, to run only on the messaging servers.</span></span>  
  
### <a name="to-configure-the-default-hosts"></a><span data-ttu-id="79477-104">既定のホストを構成するには</span><span class="sxs-lookup"><span data-stu-id="79477-104">To configure the default hosts</span></span>  
  
1.  <span data-ttu-id="79477-105">BizTalk 管理コンソールを使用して、BizTalkApplicationServer ホストからオーケストレーション サーバーのホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="79477-105">Using the BizTalk Administration Console, delete the orchestration servers host instances from the BizTalkApplicationServer host:</span></span>  
  
    -   <span data-ttu-id="79477-106">各ホスト インスタンスを右クリックし、をクリックして**停止**です。</span><span class="sxs-lookup"><span data-stu-id="79477-106">Right-click each host instance and click **Stop**.</span></span>  
  
    -   <span data-ttu-id="79477-107">各ホスト インスタンスを右クリックし、をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="79477-107">Right-click each host instance and click **Delete**.</span></span>  
  
2.  <span data-ttu-id="79477-108">BizTalk 管理コンソールを使用して、[biztalkserverisolatedhost] ホストからオーケストレーション サーバーのホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="79477-108">Using the BizTalk Administration Console, delete the orchestration servers host instances from the BizTalkServerIsolatedHost host:</span></span>  
  
    -   <span data-ttu-id="79477-109">各ホスト インスタンスを右クリックし、[削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="79477-109">Right-click each host instance and click Delete.</span></span>  
  
3.  <span data-ttu-id="79477-110">ホストを構成した後は、すべてのサーバー上のすべてのホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="79477-110">After you have configured the hosts, restart all the host instances on all the servers.</span></span>