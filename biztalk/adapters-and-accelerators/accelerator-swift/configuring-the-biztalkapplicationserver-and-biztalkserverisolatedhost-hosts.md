---
title: BizTalkApplicationServer および BizTalkServerIsolatedHost ホストの構成 |Microsoft Docs
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
ms.openlocfilehash: 462abf2b0b7f9fc0df8a1b754d0fa5803656ab88
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378528"
---
# <a name="configuring-the-biztalkapplicationserver-and-biztalkserverisolatedhost-hosts"></a><span data-ttu-id="dceff-102">BizTalkApplicationServer および BizTalkServerIsolatedHost ホストの構成</span><span class="sxs-lookup"><span data-stu-id="dceff-102">Configuring the BizTalkApplicationServer and BizTalkServerIsolatedHost Hosts</span></span>
<span data-ttu-id="dceff-103">BizTalk メッセージング サーバーには、メッセージング (送信および受信メッセージ) を制限するためには、MSMQT の送信を実行しているし、受信ハンドラー, メッセージング サーバーでのみ実行する既定のホストを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dceff-103">To limit the messaging (sending and receiving messages) to the BizTalk Messaging servers, you need to configure the default hosts, which are running the MSMQT send and receive handlers, to run only on the messaging servers.</span></span>  
  
### <a name="to-configure-the-default-hosts"></a><span data-ttu-id="dceff-104">既定のホストを構成するには</span><span class="sxs-lookup"><span data-stu-id="dceff-104">To configure the default hosts</span></span>  
  
1.  <span data-ttu-id="dceff-105">BizTalk 管理コンソールを使用して、BizTalkApplicationServer ホストからオーケストレーション サーバーのホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="dceff-105">Using the BizTalk Administration Console, delete the orchestration servers host instances from the BizTalkApplicationServer host:</span></span>  
  
    -   <span data-ttu-id="dceff-106">各ホスト インスタンスを右クリックし、をクリックして**停止**します。</span><span class="sxs-lookup"><span data-stu-id="dceff-106">Right-click each host instance and click **Stop**.</span></span>  
  
    -   <span data-ttu-id="dceff-107">各ホスト インスタンスを右クリックし、をクリックして**削除**します。</span><span class="sxs-lookup"><span data-stu-id="dceff-107">Right-click each host instance and click **Delete**.</span></span>  
  
2.  <span data-ttu-id="dceff-108">BizTalk 管理コンソールを使用して、[biztalkserverisolatedhost] ホストからオーケストレーション サーバーのホスト インスタンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="dceff-108">Using the BizTalk Administration Console, delete the orchestration servers host instances from the BizTalkServerIsolatedHost host:</span></span>  
  
    -   <span data-ttu-id="dceff-109">各ホスト インスタンスを右クリックし、[削除] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dceff-109">Right-click each host instance and click Delete.</span></span>  
  
3.  <span data-ttu-id="dceff-110">ホストを構成した後は、すべてのサーバー上のすべてのホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="dceff-110">After you have configured the hosts, restart all the host instances on all the servers.</span></span>