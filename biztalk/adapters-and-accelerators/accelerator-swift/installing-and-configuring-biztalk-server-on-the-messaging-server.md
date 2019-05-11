---
title: インストールして、メッセージング サーバーで BizTalk Server の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on BizTalk Messaging servers
- BizTalk Server, configuring
- BizTalk Messaging servers, configuring BizTalk Server
- BizTalk Messaging servers, installing BizTalk Server
ms.assetid: 8aaa1b97-90f0-4317-9403-ac8b5b9f80e3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f322ae292749f4acfa8d64ccda1ebcf5e4d62f9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378062"
---
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="a33e3-102">インストールして、メッセージング サーバーで BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="a33e3-102">Installing and Configuring BizTalk Server on the Messaging Server</span></span>
<span data-ttu-id="a33e3-103">このセクションでは、インストールを行う SWIFT ネットワークに接続するため、メッセージング サーバーとして使用する BizTalk Server を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a33e3-103">This section describes how to install and configure BizTalk Server to be used as the messaging server for connecting to the SWIFT network.</span></span>  

### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a><span data-ttu-id="a33e3-104">インストールして、メッセージング サーバーに BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="a33e3-104">To install and configure BizTalk Server on the Messaging Server</span></span>  

1. <span data-ttu-id="a33e3-105">カスタム インストール実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]他のアプリケーションで必要な場合は、EDI、ヒューマン ワークフロー サービス (HWS) および MRSR サイト以外のすべての機能を選択します。</span><span class="sxs-lookup"><span data-stu-id="a33e3-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing all the features except EDI, Human Workflow Services (HWS), and MRSR site, unless required by other applications.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a33e3-106">1 台のコンピューターの展開でこのコンピューターは、HTTP フロント エンド サービスを実行しているものと同じコンピューターに注意してください。</span><span class="sxs-lookup"><span data-stu-id="a33e3-106">Note that in single-computer deployment, this computer is the same computer as the one that runs the HTTP front-end service.</span></span>  

2. <span data-ttu-id="a33e3-107">構成を行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="a33e3-107">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="a33e3-108">インストールしないメッセージがキューをインストールするため、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] MSMQT と呼ばれる MSMQ のバージョン。</span><span class="sxs-lookup"><span data-stu-id="a33e3-108">Do not install Message Queuing, because we will be installing the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] version of MSMQ known as MSMQT.</span></span> <span data-ttu-id="a33e3-109">MSMQT の詳細については、MSDN Web サイトで BizTalk メッセージ キュー アダプター (MSMQT) 構成を参照してください。 [ http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875)します。</span><span class="sxs-lookup"><span data-stu-id="a33e3-109">For more information about MSMQT, see BizTalk Message Queuing Adapter (MSMQT) Configuration on the MSDN Web site at [http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875).</span></span>  

3. <span data-ttu-id="a33e3-110">必要な他の修正プログラムをインストール[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ガイドで利用可能な。</span><span class="sxs-lookup"><span data-stu-id="a33e3-110">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span> <span data-ttu-id="a33e3-111">このパブリケーションの時に、必要な修正プログラムはありません。</span><span class="sxs-lookup"><span data-stu-id="a33e3-111">At the time of this publication, there are no required hotfixes.</span></span>
