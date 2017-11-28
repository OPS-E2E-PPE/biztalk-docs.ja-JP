---
title: "BTAD_InstallMode |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: BTAD_InstallMode [environment variable]
ms.assetid: b0ca48b8-c672-4704-9a04-2c6f159e57be
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2bcb527bda0a8ee2bfb36b06d317d952b48e699
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="btadinstallmode"></a><span data-ttu-id="063d3-102">BTAD_InstallMode</span><span class="sxs-lookup"><span data-stu-id="063d3-102">BTAD_InstallMode</span></span>
<span data-ttu-id="063d3-103">BTAD_InstallMode は、BizTalk アプリケーションの展開のインストール モードを表します。</span><span class="sxs-lookup"><span data-stu-id="063d3-103">BTAD_InstallMode describes the installation mode for BizTalk application deployment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="063d3-104">解説</span><span class="sxs-lookup"><span data-stu-id="063d3-104">Remarks</span></span>  
 <span data-ttu-id="063d3-105">BTAD_InstallMode で使用できる値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="063d3-105">The following table describes the possible values for BTAD_InstallMode.</span></span>  
  
|<span data-ttu-id="063d3-106">値</span><span class="sxs-lookup"><span data-stu-id="063d3-106">Value</span></span>|<span data-ttu-id="063d3-107">Description</span><span class="sxs-lookup"><span data-stu-id="063d3-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="063d3-108">Install</span><span class="sxs-lookup"><span data-stu-id="063d3-108">Install</span></span>|<span data-ttu-id="063d3-109">BizTalkHostInstance (ローカル コンピューター) の作成および更新</span><span class="sxs-lookup"><span data-stu-id="063d3-109">Create or update to BizTalkHostInstance (the local computer)</span></span>|  
|<span data-ttu-id="063d3-110">[インポート]</span><span class="sxs-lookup"><span data-stu-id="063d3-110">Import</span></span>|<span data-ttu-id="063d3-111">ConfigurationDb (グループの BizTalk 管理データベース) の作成および更新</span><span class="sxs-lookup"><span data-stu-id="063d3-111">Create or update to ConfigurationDb (the BizTalk Management database for the group)</span></span>|  
|<span data-ttu-id="063d3-112">Uninstall</span><span class="sxs-lookup"><span data-stu-id="063d3-112">Uninstall</span></span>|<span data-ttu-id="063d3-113">BizTalkHostInstance (ローカル コンピューター) からの削除</span><span class="sxs-lookup"><span data-stu-id="063d3-113">Delete from BizTalkHostInstance (the local computer)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="063d3-114">参照</span><span class="sxs-lookup"><span data-stu-id="063d3-114">See Also</span></span>  
 <span data-ttu-id="063d3-115">[前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="063d3-115">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="063d3-116">環境変数が展開の状態を指定する方法</span><span class="sxs-lookup"><span data-stu-id="063d3-116">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)