---
title: SMTP アダプターに関する問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eaf39fd8-b662-4b0c-b5e8-1af02cb4f79b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5a1f88d6d096b697f8fceb3c81f8527fa5f7342
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010315"
---
# <a name="how-to-diagnose-problems-with-the-smtp-adapter"></a><span data-ttu-id="5bc1e-102">SMTP アダプターに関する問題の診断方法</span><span class="sxs-lookup"><span data-stu-id="5bc1e-102">How to Diagnose Problems with the SMTP Adapter</span></span>
<span data-ttu-id="5bc1e-103">ここでは SMTP アダプターに関する問題の診断手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="5bc1e-103">This section contains steps that can be followed to help diagnose problems with the SMTP adapter.</span></span>  
  
### <a name="check-the-smtp-log-files-of-the-smtp-server-for-errors"></a><span data-ttu-id="5bc1e-104">SMTP サーバーの SMTP ログ ファイルでエラーの有無を確認する</span><span class="sxs-lookup"><span data-stu-id="5bc1e-104">Check the SMTP log files of the SMTP Server for errors</span></span>  
  
- <span data-ttu-id="5bc1e-105">ターゲットの SMTP サーバーのログ ファイルは、SMTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="5bc1e-105">The target SMTP server log files can contain information that is helpful for troubleshooting problems with the SMTP adapter.</span></span> <span data-ttu-id="5bc1e-106">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] の SMTP ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="5bc1e-106">By default the SMTP log files on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] are located in the following directory:</span></span>  
  
   <span data-ttu-id="5bc1e-107"><em>%Windir%\\</em>system32\LogFiles\SMTPSVC1\\</span><span class="sxs-lookup"><span data-stu-id="5bc1e-107"><em>%WinDir%\\</em>system32\LogFiles\SMTPSVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="5bc1e-108">*%Windir%* SMTP サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="5bc1e-108">*%WinDir%* is a placeholder for the location of the Windows directory on the SMTP server.</span></span>  
  > 
  > [!NOTE]
  >  <span data-ttu-id="5bc1e-109">既定では、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] の SMTP ロギングは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="5bc1e-109">SMTP logging is disabled by default on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span></span> <span data-ttu-id="5bc1e-110">SMTP ロギングを有効にする方法の詳細については、Windows Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bc1e-110">For information about enabling logging for SMTP, see the Windows Server documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc1e-111">参照</span><span class="sxs-lookup"><span data-stu-id="5bc1e-111">See Also</span></span>  
 <span data-ttu-id="5bc1e-112">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="5bc1e-112">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="5bc1e-113">SMTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5bc1e-113">Troubleshooting the SMTP Adapter</span></span>](../core/troubleshooting-the-smtp-adapter.md)