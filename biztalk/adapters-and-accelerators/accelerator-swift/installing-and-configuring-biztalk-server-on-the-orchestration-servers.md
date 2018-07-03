---
title: インストールして、オーケストレーション サーバーに BizTalk Server の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on orchestration server
- orchestration server, installing BizTalk Server
ms.assetid: 72376a80-1377-4058-9478-fee668b804d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ecd5e9e4be9c9274a402b54a5bf6a2eba4ed73cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984099"
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a><span data-ttu-id="36f08-102">インストールして、オーケストレーション サーバーに BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="36f08-102">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>
<span data-ttu-id="36f08-103">このセクションでは、インストールして、メッセージの修復]、[新しい送信オーケストレーションおよび FIN 修復と調整のオーケストレーションを実行するため、オーケストレーション サーバーとして使用する BizTalk Server を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="36f08-103">This section describes how to install and configure BizTalk Server to be used as the orchestration server for running the Message Repair/New Submission orchestration and the FIN Repair and Reconciliation orchestration.</span></span>  

### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a><span data-ttu-id="36f08-104">インストールして、オーケストレーション サーバーに BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="36f08-104">To install and configure BizTalk Server on the Orchestration Server</span></span>  

1. <span data-ttu-id="36f08-105">カスタム インストール実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]他のアプリケーションで必要な場合は、EDI、ヒューマン ワークフロー サービス (HWS) および MRSR、以外のすべての機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="36f08-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR, unless required by other applications.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="36f08-106">1 台のコンピューターの展開では、このコンピューターは、HTTP フロント エンド サービスと、BizTalk メッセージング サーバーを実行しているものと同じコンピューターは。</span><span class="sxs-lookup"><span data-stu-id="36f08-106">In the single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service and the BizTalk Messaging server.</span></span>  

2. <span data-ttu-id="36f08-107">構成を行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="36f08-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="36f08-108">BizTalk オーケストレーション サーバーを構成するときに、次のガイドラインを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="36f08-108">Consider the following guidelines when configuring the BizTalk Orchestration servers:</span></span>  

   - <span data-ttu-id="36f08-109">このサーバーに接続するネットワーク アダプターを 1 つだけが必要です、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="36f08-109">This server requires only one network adapter to connect it to the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer.</span></span> <span data-ttu-id="36f08-110">HTTP フロント エンド サーバーなど、メッセージング サーバーでは、パブリックにある別のネットワーク アダプターは必要ありませんし、これにより、インターネットまたはイントラネットとエクストラネットからのハッキングに対してセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="36f08-110">It does not require another network adapter on the public side like the HTTP front-end server or the messaging server, and this makes it more secure against hacking attempts coming from the Internet or intranet/extranet.</span></span>  

3. <span data-ttu-id="36f08-111">必要な他の修正プログラムをインストール[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ガイドで利用可能な。</span><span class="sxs-lookup"><span data-stu-id="36f08-111">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>
