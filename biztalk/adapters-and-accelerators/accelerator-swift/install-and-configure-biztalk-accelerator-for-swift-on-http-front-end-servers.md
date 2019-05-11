---
title: インストールと BizTalk Accelerator を HTTP フロント エンド サーバー上の SWIFT の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on HTTP server
ms.assetid: 1deaa5f7-9da2-4d4b-8367-2d6900065839
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf35a971dbc3dad14568f880b058c1ff131a087
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377361"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a><span data-ttu-id="2414e-102">インストールと BizTalk Accelerator を HTTP フロント エンド サーバー上の SWIFT の構成</span><span class="sxs-lookup"><span data-stu-id="2414e-102">Installing and Configuring BizTalk Accelerator for SWIFT on HTTP Front-End Servers</span></span>
<span data-ttu-id="2414e-103">このセクションは、インストールして構成する方法を説明します[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]HTTP フロント エンド サーバー。</span><span class="sxs-lookup"><span data-stu-id="2414e-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the HTTP front-end servers.</span></span> <span data-ttu-id="2414e-104">これらのサーバーは主に、SWIFT ネットワークとの通信に使用します。</span><span class="sxs-lookup"><span data-stu-id="2414e-104">These servers are mainly used to communicate with the SWIFT Network.</span></span>  

### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a><span data-ttu-id="2414e-105">インストールして構成 BizTalk Accelerator for SWIFT HTTP フロント エンド サーバーに</span><span class="sxs-lookup"><span data-stu-id="2414e-105">To install and configure BizTalk Accelerator for SWIFT on the HTTP front-end server</span></span>  

1. <span data-ttu-id="2414e-106">カスタム インストール実行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2414e-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="2414e-107">インストール、 **MRSR**と**Message Repair and New Submission の Web コンポーネント**機能します。</span><span class="sxs-lookup"><span data-stu-id="2414e-107">Install the **MRSR** and **Web Components for Message Repair and New Submission** features.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="2414e-108">インストールが完了したら、構成ウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="2414e-108">After installation is complete, the Configuration Wizard starts.</span></span>  

2. <span data-ttu-id="2414e-109">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールで、構成**MCRR**と**WebService**します。</span><span class="sxs-lookup"><span data-stu-id="2414e-109">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR** and **WebService**.</span></span>  

3. <span data-ttu-id="2414e-110">フォルダーに web.config ファイルを開き、Web サーバーで、構成ウィザードの完了後に\<*ドライブ*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ メモ帳でします。</span><span class="sxs-lookup"><span data-stu-id="2414e-110">After completing the Configuration Wizard, on the Web servers, open the web.config file in the folder \<*Drive*\>:\Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ in Notepad.</span></span> <span data-ttu-id="2414e-111">"Authorization"を検索します。</span><span class="sxs-lookup"><span data-stu-id="2414e-111">Search for "Authorization".</span></span> <span data-ttu-id="2414e-112">**承認**セクションで、A4SWIFT ユーザーのグループの名前にロールの値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2414e-112">In the **Authorization** section, set the roles value to the name of the A4SWIFT users group.</span></span>
