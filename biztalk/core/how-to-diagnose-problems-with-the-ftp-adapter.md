---
title: FTP アダプターに関する問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 499d23d3-b705-4527-9929-147be157e6b3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b7b090ee9d77754cb6ed3e1f1fb5d4ae4938658
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338458"
---
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a><span data-ttu-id="8fbe2-102">FTP アダプターに関する問題を診断する方法</span><span class="sxs-lookup"><span data-stu-id="8fbe2-102">How to Diagnose Problems with the FTP Adapter</span></span>
<span data-ttu-id="8fbe2-103">このセクションには、FTP アダプターに関する問題の診断に役立つことができますの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8fbe2-103">This section contains steps that can be followed to help diagnose problems with the FTP adapter.</span></span>  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a><span data-ttu-id="8fbe2-104">FTP ログ ファイルを FTP サーバー上にエラーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8fbe2-104">Check the FTP log files on the FTP Server for errors</span></span>  
  
- <span data-ttu-id="8fbe2-105">ソースまたはターゲット FTP サーバーのログ ファイルは、FTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="8fbe2-105">The source or target FTP server log files can contain information that is helpful for troubleshooting problems with the FTP adapter.</span></span> <span data-ttu-id="8fbe2-106">既定では、Windows Server または Windows XP コンピューター上の FTP ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="8fbe2-106">By default the FTP log files on a Windows Server or Windows XP computer are located in the following directory:</span></span>  
  
   <span data-ttu-id="8fbe2-107"><em>%WinDir%\\</em>system32\LogFiles\MSFTPSVC1\\</span><span class="sxs-lookup"><span data-stu-id="8fbe2-107"><em>%WinDir%\\</em>system32\LogFiles\MSFTPSVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="8fbe2-108">*%Windir%* は FTP サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="8fbe2-108">*%WinDir%* is a placeholder for the location of the Windows directory on the FTP server.</span></span>  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a><span data-ttu-id="8fbe2-109">FTP 受信場所または送信ポートのログ記録を有効にします。</span><span class="sxs-lookup"><span data-stu-id="8fbe2-109">Enable logging for the FTP Receive location or Send Port</span></span>  
  
-   <span data-ttu-id="8fbe2-110">Ftp アダプターは構成の受信場所または送信ポートを**ログ**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="8fbe2-110">Configure the FTP receive location or send port with a **Log** folder.</span></span> <span data-ttu-id="8fbe2-111">FTP アダプターでは、詳細なログ情報をこのフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="8fbe2-111">The FTP adapter will save detailed logging information to this folder.</span></span> <span data-ttu-id="8fbe2-112">**ログ**フォルダー オプションは 使用可能な**FTP トランスポートのプロパティ**FTP トランスポートの種類で、受信場所または送信ポートを構成するときに、ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="8fbe2-112">The **Log** folder option is available on the **FTP Transport Properties** dialog box when configuring a receive location or send port with the FTP transport type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fbe2-113">参照</span><span class="sxs-lookup"><span data-stu-id="8fbe2-113">See Also</span></span>  
 [<span data-ttu-id="8fbe2-114">トラブルシューティングで使用するツールとユーティリティ</span><span class="sxs-lookup"><span data-stu-id="8fbe2-114">Tools and Utilities to Use for Troubleshooting</span></span>](../core/tools-and-utilities-to-use-for-troubleshooting.md)