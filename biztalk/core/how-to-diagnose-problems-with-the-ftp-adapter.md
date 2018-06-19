---
title: FTP アダプターに関する問題を診断する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 4e66be2e498449b1cdcc70e05c6195ccd8e4395d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248770"
---
# <a name="how-to-diagnose-problems-with-the-ftp-adapter"></a><span data-ttu-id="ab259-102">FTP アダプターに関する問題を診断する方法</span><span class="sxs-lookup"><span data-stu-id="ab259-102">How to Diagnose Problems with the FTP Adapter</span></span>
<span data-ttu-id="ab259-103">ここでは、FTP アダプターに関する問題の診断手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ab259-103">This section contains steps that can be followed to help diagnose problems with the FTP adapter.</span></span>  
  
### <a name="check-the-ftp-log-files-on-the-ftp-server-for-errors"></a><span data-ttu-id="ab259-104">FTP サーバーの FTP ログ ファイルでエラーの有無を確認する</span><span class="sxs-lookup"><span data-stu-id="ab259-104">Check the FTP log files on the FTP Server for errors</span></span>  
  
-   <span data-ttu-id="ab259-105">ソースまたはターゲット FTP サーバーのログ ファイルは、FTP アダプターに関する問題のトラブルシューティングに役立つ情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="ab259-105">The source or target FTP server log files can contain information that is helpful for troubleshooting problems with the FTP adapter.</span></span> <span data-ttu-id="ab259-106">既定では、Windows Server または Windows XP コンピューターの FTP ログ ファイルは次のディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="ab259-106">By default the FTP log files on a Windows Server or Windows XP computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="ab259-107">*%Windir%\\*system32\LogFiles\MSFTPSVC1\\</span><span class="sxs-lookup"><span data-stu-id="ab259-107">*%WinDir%\\*system32\LogFiles\MSFTPSVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ab259-108">*%Windir%* FTP サーバー上の Windows ディレクトリの場所のプレース ホルダーです。</span><span class="sxs-lookup"><span data-stu-id="ab259-108">*%WinDir%* is a placeholder for the location of the Windows directory on the FTP server.</span></span>  
  
### <a name="enable-logging-for-the-ftp-receive-location-or-send-port"></a><span data-ttu-id="ab259-109">FTP 受信場所または送信ポートのログ記録を有効にする</span><span class="sxs-lookup"><span data-stu-id="ab259-109">Enable logging for the FTP Receive location or Send Port</span></span>  
  
-   <span data-ttu-id="ab259-110">FTP を構成する受信場所または送信ポート、**ログ**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="ab259-110">Configure the FTP receive location or send port with a **Log** folder.</span></span> <span data-ttu-id="ab259-111">FTP アダプターはこのフォルダーに詳細なログ記録情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="ab259-111">The FTP adapter will save detailed logging information to this folder.</span></span> <span data-ttu-id="ab259-112">**ログ**フォルダー オプションは、 **FTP トランスポートのプロパティ**FTP トランスポートの種類で、受信場所または送信ポートを構成するときに ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="ab259-112">The **Log** folder option is available on the **FTP Transport Properties** dialog box when configuring a receive location or send port with the FTP transport type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab259-113">参照</span><span class="sxs-lookup"><span data-stu-id="ab259-113">See Also</span></span>  
 [<span data-ttu-id="ab259-114">トラブルシューティングで使用するツールとユーティリティ</span><span class="sxs-lookup"><span data-stu-id="ab259-114">Tools and Utilities to Use for Troubleshooting</span></span>](../core/tools-and-utilities-to-use-for-troubleshooting.md)