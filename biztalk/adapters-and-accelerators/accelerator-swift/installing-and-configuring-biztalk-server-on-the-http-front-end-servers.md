---
title: "インストールして、HTTP フロント エンド サーバー上の BizTalk Server の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Server
- BizTalk Server, installing on HTTP servers
ms.assetid: dc1b3675-483a-478f-b30d-62efb73ad13c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 772c240ef95c294e5e884d94b361d4cd0b102b07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-http-front-end-servers"></a><span data-ttu-id="04c7f-102">インストールして、HTTP フロント エンド サーバー上の BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="04c7f-102">Installing and Configuring BizTalk Server on the HTTP Front-End Servers</span></span>
<span data-ttu-id="04c7f-103">インストールおよび構成する方法について説明[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]MRSR サイトをホストするため、HTTP フロント エンド サーバーとして使用して、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]テンプレート フォーム。</span><span class="sxs-lookup"><span data-stu-id="04c7f-103">This section describes how to install and configure [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] to be used as the HTTP front-end server for hosting the MRSR site and the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] template forms.</span></span>  
  
### <a name="to-install-and-configure-biztalk-server-on-the-biztalk-http-front-end-servers"></a><span data-ttu-id="04c7f-104">インストールし、BizTalk HTTP フロント エンド サーバー上の BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="04c7f-104">To install and configure BizTalk Server on the BizTalk HTTP front-end servers</span></span>  
  
1.  <span data-ttu-id="04c7f-105">カスタム インストールを実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、次の機能の選択:**ビジネス ルール エンジン**と**SharePoint アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="04c7f-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing the following features: **Business Rules Engine** and **SharePoint Adapter**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04c7f-106">その他の機能は、このインストールに必要ではありません。</span><span class="sxs-lookup"><span data-stu-id="04c7f-106">Other features are not required for this installation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="04c7f-107">構成を実行する場合は、いずれかの BizTalk HTTP フロント エンド サーバーでは、BizTalk グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="04c7f-107">On one of the BizTalk HTTP front-end servers, when you perform configuration, create the BizTalk Group.</span></span>  
  
2.  <span data-ttu-id="04c7f-108">構成を行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="04c7f-108">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
3.  <span data-ttu-id="04c7f-109">必要な追加の修正プログラムをインストール[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ガイドで使用可能とします。</span><span class="sxs-lookup"><span data-stu-id="04c7f-109">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>