---
title: インストールと BizTalk Accelerator をオーケストレーション サーバーに SWIFT の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: 384548de9fb0b7a5ee4ce440869c42fdfa1e93ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209746"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-orchestration-servers"></a><span data-ttu-id="6ef4f-102">インストールと BizTalk Accelerator をオーケストレーション サーバーに SWIFT の構成</span><span class="sxs-lookup"><span data-stu-id="6ef4f-102">Installing and Configuring BizTalk Accelerator for SWIFT on Orchestration Servers</span></span>
<span data-ttu-id="6ef4f-103">インストールおよび構成する方法について説明[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]オーケストレーション サーバーにします。</span><span class="sxs-lookup"><span data-stu-id="6ef4f-103">This section describes how to install and configure [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] on the orchestration servers.</span></span> <span data-ttu-id="6ef4f-104">これらのサーバーは、FIN 修復と調整のオーケストレーションとメッセージの修復 新規送信オーケストレーションを実行する主に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6ef4f-104">These servers are mainly used to run the FIN Repair and Reconciliation orchestration and the Message Repair/New Submission orchestration.</span></span>  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-orchestration-server"></a><span data-ttu-id="6ef4f-105">インストールでおよび構成する BizTalk Accelerator for SWIFT オーケストレーション サーバー</span><span class="sxs-lookup"><span data-stu-id="6ef4f-105">To install and configure BizTalk Accelerator for SWIFT on the orchestration server</span></span>  
  
1.  <span data-ttu-id="6ef4f-106">カスタム インストールを実行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="6ef4f-106">Perform a Custom Install of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span> <span data-ttu-id="6ef4f-107">インストール、 **MRSR**機能します。</span><span class="sxs-lookup"><span data-stu-id="6ef4f-107">Install the **MRSR** feature.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6ef4f-108">このサーバーに MRSR サイトがあるないために、Message Repair and New Submission の機能の Web コンポーネントをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6ef4f-108">You do not need to install the Web Components for Message Repair and New Submission feature because this server does not have MRSR site.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6ef4f-109">インストールが完了したら、構成ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="6ef4f-109">After installation is complete, the Configuration Wizard starts.</span></span>  
  
2.  <span data-ttu-id="6ef4f-110">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールで、構成**MCRR**です。</span><span class="sxs-lookup"><span data-stu-id="6ef4f-110">In the Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] Configuration console, configure **MCRR**.</span></span>