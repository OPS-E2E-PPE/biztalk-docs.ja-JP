---
title: インストールして、HTTP フロント エンド サーバーで BizTalk Server の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Server
- BizTalk Server, installing on HTTP servers
ms.assetid: dc1b3675-483a-478f-b30d-62efb73ad13c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6f2b656a45b8ef86df96d1234eb25344cf0cbd7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377380"
---
# <a name="installing-and-configuring-biztalk-server-on-the-http-front-end-servers"></a><span data-ttu-id="435c6-102">インストールして、HTTP フロント エンド サーバーで BizTalk Server の構成</span><span class="sxs-lookup"><span data-stu-id="435c6-102">Installing and Configuring BizTalk Server on the HTTP Front-End Servers</span></span>
<span data-ttu-id="435c6-103">インストールして MRSR サイトをホストするため、HTTP フロント エンド サーバーとして使用する BizTalk Server を構成する方法について説明し、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]テンプレート フォーム。</span><span class="sxs-lookup"><span data-stu-id="435c6-103">This section describes how to install and configure BizTalk Server to be used as the HTTP front-end server for hosting the MRSR site and the [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] template forms.</span></span>  

### <a name="to-install-and-configure-biztalk-server-on-the-biztalk-http-front-end-servers"></a><span data-ttu-id="435c6-104">インストールして、BizTalk HTTP フロント エンド サーバーに BizTalk Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="435c6-104">To install and configure BizTalk Server on the BizTalk HTTP front-end servers</span></span>  

1. <span data-ttu-id="435c6-105">カスタム インストール実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次の機能を選択します。**ビジネス ルール エンジン**と**SharePoint アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="435c6-105">Perform a custom installation of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] choosing the following features: **Business Rules Engine** and **SharePoint Adapter**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="435c6-106">その他の機能では、このインストールに必要ありません。</span><span class="sxs-lookup"><span data-stu-id="435c6-106">Other features are not required for this installation.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="435c6-107">BizTalk HTTP フロント エンド サーバーのいずれかで構成を実行するときに、BizTalk グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="435c6-107">On one of the BizTalk HTTP front-end servers, when you perform configuration, create the BizTalk Group.</span></span>  

2. <span data-ttu-id="435c6-108">構成を行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="435c6-108">Perform configuration of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  

3. <span data-ttu-id="435c6-109">必要な他の修正プログラムをインストール[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ガイドで利用可能な。</span><span class="sxs-lookup"><span data-stu-id="435c6-109">Install any additional hotfixes required by [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)] as available in the installation guide.</span></span>
