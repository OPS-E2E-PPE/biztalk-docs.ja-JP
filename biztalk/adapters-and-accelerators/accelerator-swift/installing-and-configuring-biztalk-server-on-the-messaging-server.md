---
title: "インストールして、メッセージング サーバー上の BizTalk Server の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on BizTalk Messaging servers
- BizTalk Server, configuring
- BizTalk Messaging servers, configuring BizTalk Server
- BizTalk Messaging servers, installing BizTalk Server
ms.assetid: 8aaa1b97-90f0-4317-9403-ac8b5b9f80e3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2db4b3d5ff34a724b8b37a08f0bf60807d31a2b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="dfc3c-102">インストールして、メッセージング サーバー上の BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="dfc3c-102">Installing and Configuring BizTalk Server on the Messaging Server</span></span>
<span data-ttu-id="dfc3c-103">インストールおよび構成する方法について説明[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]SWIFT ネットワークに接続するために、メッセージング サーバーとして使用します。</span><span class="sxs-lookup"><span data-stu-id="dfc3c-103">This section describes how to install and configure [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] to be used as the messaging server for connecting to the SWIFT network.</span></span>  
  
### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="dfc3c-104">インストールして、メッセージング サーバー上の BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="dfc3c-104">To install and configure BizTalk Server on the Messaging Server</span></span>  
  
1.  <span data-ttu-id="dfc3c-105">カスタム インストールを実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]他のアプリケーションで必要な場合は、EDI、ヒューマン ワークフロー サービス (HWS)、および MRSR サイト以外のすべての機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="dfc3c-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR site, unless required by other applications.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfc3c-106">1 台のコンピューター展開でこのコンピューターは、HTTP フロント エンド サービスを実行しているものと同じコンピューターに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dfc3c-106">Note that in single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service.</span></span>  
  
2.  <span data-ttu-id="dfc3c-107">構成を行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dfc3c-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfc3c-108">インストールしないメッセージがキューをインストールするため、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] MSMQT と呼ばれる MSMQ のバージョン。</span><span class="sxs-lookup"><span data-stu-id="dfc3c-108">Do not install Message Queuing, because we will be installing the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] version of MSMQ known as MSMQT.</span></span> <span data-ttu-id="dfc3c-109">MSMQT の詳細については、MSDN Web サイトで BizTalk メッセージ キュー アダプター (MSMQT) 構成を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875)です。</span><span class="sxs-lookup"><span data-stu-id="dfc3c-109">For more information about MSMQT, see BizTalk Message Queuing Adapter (MSMQT) Configuration on the MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875).</span></span>  
  
3.  <span data-ttu-id="dfc3c-110">必要な追加の修正プログラムをインストール[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ガイドで使用可能とします。</span><span class="sxs-lookup"><span data-stu-id="dfc3c-110">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span> <span data-ttu-id="dfc3c-111">このパブリケーションの時に、必要な修正プログラムはありません。</span><span class="sxs-lookup"><span data-stu-id="dfc3c-111">At the time of this publication, there are no required hotfixes.</span></span>