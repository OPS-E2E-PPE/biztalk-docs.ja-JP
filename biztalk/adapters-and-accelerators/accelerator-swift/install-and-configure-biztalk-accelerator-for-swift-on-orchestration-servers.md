---
title: インストールと BizTalk Accelerator をオーケストレーション サーバーに SWIFT の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestration server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on orchestration server
ms.assetid: 127113ae-46b4-4290-a2c1-6a3db04cd178
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dcf11738d89600c190cdec99375348404f47f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377347"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-orchestration-servers"></a><span data-ttu-id="2dd9d-102">インストールと SWIFT オーケストレーション サーバー上の BizTalk アクセラレータを構成します。</span><span class="sxs-lookup"><span data-stu-id="2dd9d-102">Installing and Configuring BizTalk Accelerator for SWIFT on Orchestration Servers</span></span>
<span data-ttu-id="2dd9d-103">このセクションは、インストールして構成する方法を説明します[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]オーケストレーション サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="2dd9d-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the orchestration servers.</span></span> <span data-ttu-id="2dd9d-104">これらのサーバーは主に、FIN Repair and Reconciliation のオーケストレーションとメッセージの修復]、[新しい送信オーケストレーションの実行に使用します。</span><span class="sxs-lookup"><span data-stu-id="2dd9d-104">These servers are mainly used to run the FIN Repair and Reconciliation orchestration and the Message Repair/New Submission orchestration.</span></span>  

### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-orchestration-server"></a><span data-ttu-id="2dd9d-105">インストールし、BizTalk Accelerator for SWIFT サーバーで構成するオーケストレーション</span><span class="sxs-lookup"><span data-stu-id="2dd9d-105">To install and configure BizTalk Accelerator for SWIFT on the orchestration server</span></span>  

1. <span data-ttu-id="2dd9d-106">カスタム インストール実行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2dd9d-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="2dd9d-107">インストール、 **MRSR**機能します。</span><span class="sxs-lookup"><span data-stu-id="2dd9d-107">Install the **MRSR** feature.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="2dd9d-108">このサーバーに MRSR サイトがあるないために、Message Repair and New Submission の機能の Web コンポーネントをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2dd9d-108">You do not need to install the Web Components for Message Repair and New Submission feature because this server does not have MRSR site.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="2dd9d-109">インストールが完了したら、構成ウィザードが開始されます。</span><span class="sxs-lookup"><span data-stu-id="2dd9d-109">After installation is complete, the Configuration Wizard starts.</span></span>  

2. <span data-ttu-id="2dd9d-110">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールで、構成**MCRR**します。</span><span class="sxs-lookup"><span data-stu-id="2dd9d-110">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR**.</span></span>
