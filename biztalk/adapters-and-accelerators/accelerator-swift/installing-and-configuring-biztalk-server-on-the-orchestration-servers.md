---
title: "インストールして、オーケストレーション サーバー上の BizTalk Server の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on orchestration server
- orchestration server, installing BizTalk Server
ms.assetid: 72376a80-1377-4058-9478-fee668b804d0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d872d58c72110d7af22c6d64e7d212fbee53fae9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a><span data-ttu-id="6f15f-102">インストールして、オーケストレーション サーバーに BizTalk Server を構成します。</span><span class="sxs-lookup"><span data-stu-id="6f15f-102">Installing and Configuring BizTalk Server on the Orchestration Servers</span></span>
<span data-ttu-id="6f15f-103">インストールおよび構成する方法について説明[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]修復 新規のメッセージの発信オーケストレーションおよび FIN 修復と調整のオーケストレーションを実行するオーケストレーション サーバーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="6f15f-103">This section describes how to install and configure [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] to be used as the orchestration server for running the Message Repair/New Submission orchestration and the FIN Repair and Reconciliation orchestration.</span></span>  
  
### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a><span data-ttu-id="6f15f-104">インストールして、オーケストレーション サーバー上の BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="6f15f-104">To install and configure BizTalk Server on the Orchestration Server</span></span>  
  
1.  <span data-ttu-id="6f15f-105">カスタム インストールを実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]他のアプリケーションで必要な場合は、EDI、ヒューマン ワークフロー サービス (HWS)、および MRSR、以外のすべての機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f15f-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR, unless required by other applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6f15f-106">1 台のコンピューター展開では、このコンピューターは、HTTP フロント エンド サービスと、BizTalk メッセージング サーバーを実行しているものと同じコンピューターは。</span><span class="sxs-lookup"><span data-stu-id="6f15f-106">In the single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service and the BizTalk Messaging server.</span></span>  
  
2.  <span data-ttu-id="6f15f-107">構成を行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6f15f-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6f15f-108">BizTalk オーケストレーション サーバーを構成するときに、次のガイドラインを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="6f15f-108">Consider the following guidelines when configuring the BizTalk Orchestration servers:</span></span>  
  
    -   <span data-ttu-id="6f15f-109">このサーバーに接続するための 1 つのみのネットワーク アダプターが必要、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="6f15f-109">This server requires only one network adapter to connect it to the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] computer.</span></span> <span data-ttu-id="6f15f-110">パブリック HTTP フロント エンド サーバーなど、メッセージング サーバー側で別のネットワーク アダプターは必要ありませんし、これにより、インターネットまたはイントラネットとエクストラネットからのハッキングに対してセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="6f15f-110">It does not require another network adapter on the public side like the HTTP front-end server or the messaging server, and this makes it more secure against hacking attempts coming from the Internet or intranet/extranet.</span></span>  
  
3.  <span data-ttu-id="6f15f-111">必要な追加の修正プログラムをインストール[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ガイドで使用可能とします。</span><span class="sxs-lookup"><span data-stu-id="6f15f-111">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>