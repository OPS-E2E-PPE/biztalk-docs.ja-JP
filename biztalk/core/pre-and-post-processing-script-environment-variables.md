---
title: 前処理および後処理のスクリプト環境変数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, post-processing
- scripts, pre-processing
- scripts, variables
ms.assetid: 4185fb68-b00d-4875-82fd-a040905f84e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af8834f70db30ea5f7609383846db3970582729e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396229"
---
# <a name="pre--and-post-processing-script-environment-variables"></a><span data-ttu-id="2902f-102">処理前および処理後のスクリプト環境変数</span><span class="sxs-lookup"><span data-stu-id="2902f-102">Pre- and Post-processing Script Environment Variables</span></span>
<span data-ttu-id="2902f-103">このセクションのトピックでは、処理前および処理後のスクリプトでアクセスできる環境変数について説明します。</span><span class="sxs-lookup"><span data-stu-id="2902f-103">The topics in this section describe the environment variables that pre- and post-processing scripts can access.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2902f-104">Windows の標準機能では、環境変数の名前の大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="2902f-104">Per Windows standards, the name of the environment variable is not case-sensitive.</span></span> <span data-ttu-id="2902f-105">ただし、変数値では大文字と小文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2902f-105">Variable values, however, are case-sensitive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2902f-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2902f-106">In This Section</span></span>  
  
-   [<span data-ttu-id="2902f-107">BTAD_ChangeRequestAction</span><span class="sxs-lookup"><span data-stu-id="2902f-107">BTAD_ChangeRequestAction</span></span>](../core/btad-changerequestaction.md)  
  
-   [<span data-ttu-id="2902f-108">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="2902f-108">BTAD_HostClass</span></span>](../core/btad-hostclass.md)  
  
-   [<span data-ttu-id="2902f-109">BTAD_InstallMode</span><span class="sxs-lookup"><span data-stu-id="2902f-109">BTAD_InstallMode</span></span>](../core/btad-installmode.md)  
  
-   [<span data-ttu-id="2902f-110">BTAD_InstallDir</span><span class="sxs-lookup"><span data-stu-id="2902f-110">BTAD_InstallDir</span></span>](../core/btad-installdir.md)  
  
-   [<span data-ttu-id="2902f-111">BTAD_ApplicationName</span><span class="sxs-lookup"><span data-stu-id="2902f-111">BTAD_ApplicationName</span></span>](../core/btad-applicationname.md)  
  
-   [<span data-ttu-id="2902f-112">BTAD_SilentMode</span><span class="sxs-lookup"><span data-stu-id="2902f-112">BTAD_SilentMode</span></span>](../core/btad-silentmode.md)  
  
-   [<span data-ttu-id="2902f-113">BTAD_Server</span><span class="sxs-lookup"><span data-stu-id="2902f-113">BTAD_Server</span></span>](../core/btad-server.md)  
  
-   [<span data-ttu-id="2902f-114">BTAD_Database</span><span class="sxs-lookup"><span data-stu-id="2902f-114">BTAD_Database</span></span>](../core/btad-database.md)