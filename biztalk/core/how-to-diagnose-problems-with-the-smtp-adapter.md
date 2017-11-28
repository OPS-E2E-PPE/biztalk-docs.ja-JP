---
title: "SMTP アダプターに関する問題を診断する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eaf39fd8-b662-4b0c-b5e8-1af02cb4f79b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a41a347534c07b522de5fc073933758870bf8a8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-diagnose-problems-with-the-smtp-adapter"></a><span data-ttu-id="978dd-102">SMTP アダプターに関する問題の診断方法</span><span class="sxs-lookup"><span data-stu-id="978dd-102">How to Diagnose Problems with the SMTP Adapter</span></span>
<span data-ttu-id="978dd-103">ここでは SMTP アダプターに関する問題の診断手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="978dd-103">This section contains steps that can be followed to help diagnose problems with the SMTP adapter.</span></span>  
  
### <a name="check-the-smtp-log-files-of-the-smtp-server-for-errors"></a><span data-ttu-id="978dd-104">SMTP サーバーの SMTP ログ ファイルでエラーの有無を確認する</span><span class="sxs-lookup"><span data-stu-id="978dd-104">Check the SMTP log files of the SMTP Server for errors</span></span>  
  
-   <span data-ttu-id="978dd-105">ターゲットの SMTP サーバーのログ ファイルには、SMTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="978dd-105">The target SMTP server log files can contain information that is helpful for troubleshooting problems with the SMTP adapter.</span></span> <span data-ttu-id="978dd-106">既定では、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] の SMTP ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="978dd-106">By default the SMTP log files on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] are located in the following directory:</span></span>  
  
     <span data-ttu-id="978dd-107">*%Windir%\\*system32\LogFiles\SMTPSVC1\\</span><span class="sxs-lookup"><span data-stu-id="978dd-107">*%WinDir%\\*system32\LogFiles\SMTPSVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="978dd-108">*%Windir%* SMTP サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="978dd-108">*%WinDir%* is a placeholder for the location of the Windows directory on the SMTP server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="978dd-109">既定では、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] の SMTP ロギングは無効になっています。</span><span class="sxs-lookup"><span data-stu-id="978dd-109">SMTP logging is disabled by default on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span></span> <span data-ttu-id="978dd-110">SMTP ロギングを有効にする方法の詳細については、Windows Server のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="978dd-110">For information about enabling logging for SMTP, see the Windows Server documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="978dd-111">参照</span><span class="sxs-lookup"><span data-stu-id="978dd-111">See Also</span></span>  
 <span data-ttu-id="978dd-112">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="978dd-112">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="978dd-113">SMTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="978dd-113">Troubleshooting the SMTP Adapter</span></span>](../core/troubleshooting-the-smtp-adapter.md)