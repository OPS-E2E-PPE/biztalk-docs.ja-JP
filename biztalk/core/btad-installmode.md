---
title: BTAD_InstallMode |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAD_InstallMode [environment variable]
ms.assetid: b0ca48b8-c672-4704-9a04-2c6f159e57be
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94b86412d081602ab77330bb4a6b6e567d662d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357819"
---
# <a name="btadinstallmode"></a><span data-ttu-id="6094c-102">BTAD_InstallMode</span><span class="sxs-lookup"><span data-stu-id="6094c-102">BTAD_InstallMode</span></span>
<span data-ttu-id="6094c-103">BTAD_InstallMode は、BizTalk アプリケーションの展開のインストール モードを表します。</span><span class="sxs-lookup"><span data-stu-id="6094c-103">BTAD_InstallMode describes the installation mode for BizTalk application deployment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6094c-104">コメント</span><span class="sxs-lookup"><span data-stu-id="6094c-104">Remarks</span></span>  
 <span data-ttu-id="6094c-105">BTAD_InstallMode で使用できる値を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="6094c-105">The following table describes the possible values for BTAD_InstallMode.</span></span>  
  
|<span data-ttu-id="6094c-106">値</span><span class="sxs-lookup"><span data-stu-id="6094c-106">Value</span></span>|<span data-ttu-id="6094c-107">説明</span><span class="sxs-lookup"><span data-stu-id="6094c-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="6094c-108">インストール</span><span class="sxs-lookup"><span data-stu-id="6094c-108">Install</span></span>|<span data-ttu-id="6094c-109">BizTalkHostInstance (ローカル コンピューター) の作成および更新</span><span class="sxs-lookup"><span data-stu-id="6094c-109">Create or update to BizTalkHostInstance (the local computer)</span></span>|  
|<span data-ttu-id="6094c-110">[インポート]</span><span class="sxs-lookup"><span data-stu-id="6094c-110">Import</span></span>|<span data-ttu-id="6094c-111">ConfigurationDb (グループの BizTalk 管理データベース) の作成および更新</span><span class="sxs-lookup"><span data-stu-id="6094c-111">Create or update to ConfigurationDb (the BizTalk Management database for the group)</span></span>|  
|<span data-ttu-id="6094c-112">アンインストール</span><span class="sxs-lookup"><span data-stu-id="6094c-112">Uninstall</span></span>|<span data-ttu-id="6094c-113">BizTalkHostInstance (ローカル コンピューター) からの削除</span><span class="sxs-lookup"><span data-stu-id="6094c-113">Delete from BizTalkHostInstance (the local computer)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6094c-114">参照</span><span class="sxs-lookup"><span data-stu-id="6094c-114">See Also</span></span>  
 <span data-ttu-id="6094c-115">[前処理および後処理のスクリプト環境変数](../core/pre-and-post-processing-script-environment-variables.md) </span><span class="sxs-lookup"><span data-stu-id="6094c-115">[Pre- and Post-processing Script Environment Variables](../core/pre-and-post-processing-script-environment-variables.md) </span></span>  
 [<span data-ttu-id="6094c-116">環境変数と展開状態の対応関係</span><span class="sxs-lookup"><span data-stu-id="6094c-116">How Environment Variables Indicate Deployment State</span></span>](../core/how-environment-variables-indicate-deployment-state.md)