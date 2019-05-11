---
title: BizTalk Server2 の管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 977e2685-a914-422a-97f7-d0c23717f010
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c84faae692cf514b7a9049e2c1ae4165ebce26b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396247"
---
# <a name="managing-biztalk-server"></a><span data-ttu-id="a3c09-102">BizTalk Server の管理</span><span class="sxs-lookup"><span data-stu-id="a3c09-102">Managing BizTalk Server</span></span>
<span data-ttu-id="a3c09-103">このセクションでは、運用環境で BizTalk Server システムを管理するためのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="a3c09-103">This section provides guidance for managing a BizTalk Server system in a production environment.</span></span> <span data-ttu-id="a3c09-104">一般に次の手順では、デプロイ後に BizTalk アプリケーションを使用するとします。</span><span class="sxs-lookup"><span data-stu-id="a3c09-104">The procedures that follow generally assume you are working with a BizTalk application after deployment.</span></span> <span data-ttu-id="a3c09-105">これらの手順では、ベスト プラクティスと、次のルーチン処理の概念について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3c09-105">These procedures describe best practices and concepts for routine operations including the following:</span></span>  
  
- <span data-ttu-id="a3c09-106">チェックリストと運用環境に BizTalk アプリケーションをデプロイするための手順。</span><span class="sxs-lookup"><span data-stu-id="a3c09-106">Checklists and procedures for deploying a BizTalk application into a production environment.</span></span>  
  
- <span data-ttu-id="a3c09-107">チェックリストと運用環境にデプロイ後に BizTalk アプリケーションを更新するための手順。</span><span class="sxs-lookup"><span data-stu-id="a3c09-107">Checklists and procedures for updating a BizTalk application after deployment to a production environment.</span></span>  
  
- <span data-ttu-id="a3c09-108">をインストールする手順では、構成、およびデジタル暗号化証明書を管理します。</span><span class="sxs-lookup"><span data-stu-id="a3c09-108">Procedures to install, configure, and manage digital encryption certificates.</span></span>  
  
- <span data-ttu-id="a3c09-109">移動する手順[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SQL Server の 1 つのインスタンスから別のデータベース。</span><span class="sxs-lookup"><span data-stu-id="a3c09-109">Procedures for moving [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases from one instance of SQL Server to another.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a3c09-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a3c09-110">In This Section</span></span>  
  
-   [<span data-ttu-id="a3c09-111">アプリケーションの管理</span><span class="sxs-lookup"><span data-stu-id="a3c09-111">Managing Applications</span></span>](../technical-guides/managing-applications.md)  
  
-   [<span data-ttu-id="a3c09-112">Certificates2 を管理します。</span><span class="sxs-lookup"><span data-stu-id="a3c09-112">Managing Certificates2</span></span>](../technical-guides/managing-certificates2.md)  
  
-   [<span data-ttu-id="a3c09-113">データベースの移動</span><span class="sxs-lookup"><span data-stu-id="a3c09-113">Moving Databases</span></span>](../technical-guides/moving-databases.md)