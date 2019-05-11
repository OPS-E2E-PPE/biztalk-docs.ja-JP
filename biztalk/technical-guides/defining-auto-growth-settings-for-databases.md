---
title: データベースの自動拡張設定の定義 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dd86dd49-6505-4673-b413-d3af729dfca9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c2070ae827136a5b03cb51ef0697db0180fe5b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305946"
---
# <a name="define-auto-growth-settings-for-databases"></a><span data-ttu-id="9988c-102">データベースの自動拡張設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="9988c-102">Define Auto-Growth Settings for Databases</span></span>
<span data-ttu-id="9988c-103">データベース自動拡張は、固定の代わりに、メッセージ ボックス データベースおよび BizTalk 追跡データベースの特にのパーセント値のメガバイト数に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9988c-103">You should set database auto-growth to a fixed number of megabytes instead of to a percentage, especially for the MessageBox and BizTalk Tracking databases.</span></span> <span data-ttu-id="9988c-104">BizTalk アプリケーションとスループットに応じて、メッセージ ボックス データベースと追跡データベースを非常に大きく取得できます。</span><span class="sxs-lookup"><span data-stu-id="9988c-104">Depending on your BizTalk application and throughput, the MessageBox and Tracking databases can get quite large.</span></span> <span data-ttu-id="9988c-105">自動拡張をパーセンテージに設定した場合、自動拡張相当する場合がもします。</span><span class="sxs-lookup"><span data-stu-id="9988c-105">If you set auto-growth to a percentage, then the auto-growth can be substantial as well.</span></span>  
  
## <a name="how-instant-file-initialization-works"></a><span data-ttu-id="9988c-106">どのインスタント ファイルの初期化のしくみ</span><span class="sxs-lookup"><span data-stu-id="9988c-106">How Instant File Initialization Works</span></span>  
 <span data-ttu-id="9988c-107">SQL Server には、ファイルのサイズが大きくとき、は、新しいスペースまず初期化を可能にする前に、必要があります。</span><span class="sxs-lookup"><span data-stu-id="9988c-107">When SQL Server increases the size of a file, it must first initialize the new space before it can be used.</span></span> <span data-ttu-id="9988c-108">これは、空のページで、新しい領域の入力を含むブロッキング操作です。</span><span class="sxs-lookup"><span data-stu-id="9988c-108">This is a blocking operation that involves filling the new space with empty pages.</span></span> <span data-ttu-id="9988c-109">Windows 上の SQL Server は、「ファイルの瞬時初期化します。」をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="9988c-109">SQL Server on Windows supports “instant file initialization.”</span></span> <span data-ttu-id="9988c-110">これは、ファイルの拡張操作のパフォーマンスに与える影響を大幅に削減できます。</span><span class="sxs-lookup"><span data-stu-id="9988c-110">This can greatly reduce the performance impact of a file growth operation.</span></span> <span data-ttu-id="9988c-111">詳細については、「 [データベース ファイルの初期化](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9988c-111">For more information, see [Database File Initialization](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization).</span></span> <span data-ttu-id="9988c-112">このトピックでは、ファイルの瞬時初期化を有効にするに必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="9988c-112">This topic outlines the steps that must be taken to enable instant file initialization.</span></span>  
  
## <a name="enable-instant-file-initialization"></a><span data-ttu-id="9988c-113">ファイルの瞬時初期化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="9988c-113">Enable Instant File Initialization</span></span>  
 <span data-ttu-id="9988c-114">即時有効にする手順は、初期化ファイルを参照してください[データベース ファイルの初期化](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization)します。</span><span class="sxs-lookup"><span data-stu-id="9988c-114">For steps on enabling instant file initialization, see [Database File Initialization](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization).</span></span> <span data-ttu-id="9988c-115">ファイル グループを作成すると、適切なファイル グループに BizTalk Server データベース テーブル、インデックス、およびログ ファイルを移動する、推奨事項に従い、 [BizTalk パフォーマンス最適化ガイド](../technical-guides/biztalk-server-2013-performance-optimization-guide.md)します。</span><span class="sxs-lookup"><span data-stu-id="9988c-115">For creating file groups and moving the BizTalk Server database tables, indexes, and log files into the appropriate file groups, follow the recommendations in the [BizTalk performance optimization guide](../technical-guides/biztalk-server-2013-performance-optimization-guide.md).</span></span> <span data-ttu-id="9988c-116">理想的にはファイル グループをサポートしているファイルのサイズを事前に割り当てられるし、可能であれば、静的なサイズに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9988c-116">Ideally the size of files supporting the file groups should be pre-allocated and if possible, set to a static size.</span></span>  
  
 <span data-ttu-id="9988c-117">ファイルを構成し、システムが新しい静的サイズが決定的確立されていない場合、**自動拡張を有効にする**オプションし、ファイルの拡張を指定**メガバイト単位で**します。</span><span class="sxs-lookup"><span data-stu-id="9988c-117">If the system is new and the static sizes have not been definitively established, then configure files with the **Enable Autogrowth** option and specify file growth **In Megabytes**.</span></span> <span data-ttu-id="9988c-118">拡張増分値は、100 MB (サイズの大きいファイル) を (中規模ファイル用)、10 MB または 1 MB (小さなファイル) の以下通常場合があります。</span><span class="sxs-lookup"><span data-stu-id="9988c-118">The growth increment should generally be no larger than 100 MB (for large files), 10 MB (for medium-sized files), or 1 MB (for small files).</span></span>
