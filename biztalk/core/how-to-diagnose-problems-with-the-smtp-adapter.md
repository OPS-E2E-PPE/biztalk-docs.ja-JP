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
ms.openlocfilehash: cd84acb26dfc70f5f2d84e93bb700ab48ea2fa03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338329"
---
# <a name="how-to-diagnose-problems-with-the-smtp-adapter"></a><span data-ttu-id="2de26-102">SMTP アダプターに関する問題の診断方法</span><span class="sxs-lookup"><span data-stu-id="2de26-102">How to Diagnose Problems with the SMTP Adapter</span></span>
<span data-ttu-id="2de26-103">このセクションには、SMTP アダプターに関する問題の診断に役立つことができますの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2de26-103">This section contains steps that can be followed to help diagnose problems with the SMTP adapter.</span></span>  
  
### <a name="check-the-smtp-log-files-of-the-smtp-server-for-errors"></a><span data-ttu-id="2de26-104">SMTP サーバーの SMTP ログ ファイルにエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="2de26-104">Check the SMTP log files of the SMTP Server for errors</span></span>  
  
- <span data-ttu-id="2de26-105">ターゲットの SMTP サーバーのログ ファイルは、SMTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="2de26-105">The target SMTP server log files can contain information that is helpful for troubleshooting problems with the SMTP adapter.</span></span> <span data-ttu-id="2de26-106">既定では、SMTP ログ ファイル[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="2de26-106">By default the SMTP log files on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] are located in the following directory:</span></span>  
  
   <span data-ttu-id="2de26-107"><em>%WinDir%\\</em>system32\LogFiles\SMTPSVC1\\</span><span class="sxs-lookup"><span data-stu-id="2de26-107"><em>%WinDir%\\</em>system32\LogFiles\SMTPSVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="2de26-108">*%Windir%* SMTP サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="2de26-108">*%WinDir%* is a placeholder for the location of the Windows directory on the SMTP server.</span></span>  
  > 
  > [!NOTE]
  >  <span data-ttu-id="2de26-109">既定の SMTP ログ記録が無効に[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2de26-109">SMTP logging is disabled by default on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span></span> <span data-ttu-id="2de26-110">SMTP のログ記録を有効にする方法については、Windows Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2de26-110">For information about enabling logging for SMTP, see the Windows Server documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de26-111">参照</span><span class="sxs-lookup"><span data-stu-id="2de26-111">See Also</span></span>  
 <span data-ttu-id="2de26-112">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="2de26-112">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="2de26-113">SMTP アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2de26-113">Troubleshooting the SMTP Adapter</span></span>](../core/troubleshooting-the-smtp-adapter.md)