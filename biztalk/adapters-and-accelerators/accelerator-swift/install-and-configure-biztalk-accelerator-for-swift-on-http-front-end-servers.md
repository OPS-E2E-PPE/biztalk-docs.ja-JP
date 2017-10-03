---
title: "インストールと BizTalk Accelerator を HTTP フロント エンド サーバーに SWIFT の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on HTTP server
ms.assetid: 1deaa5f7-9da2-4d4b-8367-2d6900065839
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe0a320f9f60f72975faf903c1355b8730840b26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a><span data-ttu-id="b4b11-102">インストールと BizTalk Accelerator を HTTP フロント エンド サーバーに SWIFT の構成</span><span class="sxs-lookup"><span data-stu-id="b4b11-102">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>
<span data-ttu-id="b4b11-103">インストールおよび構成する方法について説明[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]HTTP フロント エンド サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="b4b11-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the HTTP front-end servers.</span></span> <span data-ttu-id="b4b11-104">これらのサーバーは主に SWIFT ネットワークとの通信に使用します。</span><span class="sxs-lookup"><span data-stu-id="b4b11-104">These servers are mainly used to communicate with the SWIFT Network.</span></span>  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a><span data-ttu-id="b4b11-105">インストールでおよび構成する BizTalk Accelerator for SWIFT HTTP フロント エンド サーバー</span><span class="sxs-lookup"><span data-stu-id="b4b11-105">To install and configure BizTalk Accelerator for SWIFT on the HTTP front-end server</span></span>  
  
1.  <span data-ttu-id="b4b11-106">カスタム インストールを実行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b4b11-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="b4b11-107">インストール、 **MRSR**と**Message Repair and New Submission の Web コンポーネント**機能します。</span><span class="sxs-lookup"><span data-stu-id="b4b11-107">Install the **MRSR** and **Web Components for Message Repair and New Submission** features.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b4b11-108">インストールが完了したら、構成ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="b4b11-108">After installation is complete, the Configuration Wizard starts.</span></span>  
  
2.  <span data-ttu-id="b4b11-109">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールで、構成**MCRR**と**WebService**です。</span><span class="sxs-lookup"><span data-stu-id="b4b11-109">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR** and **WebService**.</span></span>  
  
3.  <span data-ttu-id="b4b11-110">Web サーバーで、構成ウィザードの完了後に、フォルダーに web.config ファイルを開きます。 \<*ドライブ*>: \Program Files\Microsoft[!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]メモ帳で \Service\ です。</span><span class="sxs-lookup"><span data-stu-id="b4b11-110">After completing the Configuration Wizard, on the Web servers, open the web.config file in the folder \<*Drive*>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ in Notepad.</span></span> <span data-ttu-id="b4b11-111">"Authorization"を検索します。</span><span class="sxs-lookup"><span data-stu-id="b4b11-111">Search for "Authorization".</span></span> <span data-ttu-id="b4b11-112">**承認**セクションで、ロール値 A4SWIFT users グループの名前を設定します。</span><span class="sxs-lookup"><span data-stu-id="b4b11-112">In the **Authorization** section, set the roles value to the name of the A4SWIFT users group.</span></span>