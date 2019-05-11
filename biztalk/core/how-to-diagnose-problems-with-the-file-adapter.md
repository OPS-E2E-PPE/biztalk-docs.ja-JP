---
title: ファイル アダプターに関する問題を診断する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f06089a5-4747-4879-a796-157088868dba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 017d9f2027a42bb804b6baf4b2a14915e4a525de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385222"
---
# <a name="how-to-diagnose-problems-with-the-file-adapter"></a><span data-ttu-id="9a8b2-102">ファイル アダプターに関する問題の診断方法</span><span class="sxs-lookup"><span data-stu-id="9a8b2-102">How to Diagnose Problems with the File Adapter</span></span>
<span data-ttu-id="9a8b2-103">このセクションには、ファイル アダプターに関する問題の診断に役立つことができますの手順が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9a8b2-103">This section contains steps that can be followed to help diagnose problems with the File adapter.</span></span>  
  
### <a name="run-the-filemon-utility-to-diagnose-errors-that-occur-using-the-file-receive-or-file-send-adapter"></a><span data-ttu-id="9a8b2-104">ファイル受信アダプターまたはファイル送信アダプターを使用して発生したエラーを診断する FileMon ユーティリティを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a8b2-104">Run the FileMon Utility to diagnose errors that occur using the File Receive or File Send Adapter</span></span>  
  
1.  <span data-ttu-id="9a8b2-105">FileMon ユーティリティをダウンロード[www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235)します。</span><span class="sxs-lookup"><span data-stu-id="9a8b2-105">Download the FileMon utility from [www.sysinternals.com](http://go.microsoft.com/fwlink/?LinkId=66235).</span></span>  
  
2.  <span data-ttu-id="9a8b2-106">読み取るか、ファイル アダプターによって書き込まれる、または共有にフォルダーをホストするサーバー上のユーティリティがされている Filemon をインストールします。</span><span class="sxs-lookup"><span data-stu-id="9a8b2-106">Install the Filemon utility on the server that hosts the folder or share that is being read from or written to by the File Adapter.</span></span>  
  
3.  <span data-ttu-id="9a8b2-107">Filemon ユーティリティを起動し、BizTalk ホスト インスタンス (BTSNTSvc.exe など) で、ファイル アダプターのハンドラーが実行されているによるファイル アクセスのみを監視するフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="9a8b2-107">Launch the Filemon utility and apply a filter to monitor only file accesses that are being made by the BizTalk Host instance that the file adapter handlers are running in (for example BTSNTSvc.exe).</span></span>  
  
4.  <span data-ttu-id="9a8b2-108">問題の原因となったシナリオを実行します。</span><span class="sxs-lookup"><span data-stu-id="9a8b2-108">Run the scenario that caused the problem.</span></span>  
  
5.  <span data-ttu-id="9a8b2-109">ファイルの Filemon ユーティリティの監視を無効にし、生成されたログ ファイルをディスクに保存します。</span><span class="sxs-lookup"><span data-stu-id="9a8b2-109">Disable file monitoring in the Filemon utility, then save the generated log file to disk.</span></span>  
  
6.  <span data-ttu-id="9a8b2-110">生成されたログ ファイルで、エラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a8b2-110">Review the generated log file for any errors.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a8b2-111">FileMon は、Microsoft ではサポートされていないと、Microsoft はこのプログラムの適合性に関する保証をいたしません。</span><span class="sxs-lookup"><span data-stu-id="9a8b2-111">FileMon is not supported by Microsoft, and Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="9a8b2-112">このプログラムは、ユーザー自身の責任で使用してください。</span><span class="sxs-lookup"><span data-stu-id="9a8b2-112">Use of this program is entirely at your own risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a8b2-113">参照</span><span class="sxs-lookup"><span data-stu-id="9a8b2-113">See Also</span></span>  
 <span data-ttu-id="9a8b2-114">[トラブルシューティングで使用するツールとユーティリティ](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="9a8b2-114">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 [<span data-ttu-id="9a8b2-115">ファイル アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="9a8b2-115">Troubleshooting the File Adapter</span></span>](../core/troubleshooting-the-file-adapter.md)