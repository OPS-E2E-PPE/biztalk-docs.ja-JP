---
title: "データベースの自動拡張設定を定義する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd86dd49-6505-4673-b413-d3af729dfca9
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e39de58751615e0465ce543368f47c1acd42ebc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="defining-auto-growth-settings-for-databases"></a><span data-ttu-id="fb854-102">データベースの自動拡張設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="fb854-102">Defining Auto-Growth Settings for Databases</span></span>
<span data-ttu-id="fb854-103">データベースの自動拡張は、の代わりに、メッセージ ボックス データベースと BizTalk 追跡データベースの特にのパーセント値のメガバイト数が固定に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb854-103">You should set database auto-growth to a fixed number of megabytes instead of to a percentage, especially for the MessageBox and BizTalk Tracking databases.</span></span> <span data-ttu-id="fb854-104">BizTalk アプリケーションとスループット、に応じて、メッセージ ボックス データベースおよび追跡データベースを非常に大きい取得できます。</span><span class="sxs-lookup"><span data-stu-id="fb854-104">Depending on your BizTalk application and throughput, the MessageBox and Tracking databases can get quite large.</span></span> <span data-ttu-id="fb854-105">パーセンテージを自動拡張を設定した場合、自動拡張できますかなり大きくなる場合もします。</span><span class="sxs-lookup"><span data-stu-id="fb854-105">If you set auto-growth to a percentage, then the auto-growth can be substantial as well.</span></span>  
  
## <a name="how-instant-file-initialization-works"></a><span data-ttu-id="fb854-106">どの瞬時ファイル初期化 Works</span><span class="sxs-lookup"><span data-stu-id="fb854-106">How Instant File Initialization Works</span></span>  
 <span data-ttu-id="fb854-107">SQL Server では、ファイルのサイズを大きく、ときに、新しい領域最初初期化を使用する前に、必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb854-107">When SQL Server increases the size of a file, it must first initialize the new space before it can be used.</span></span> <span data-ttu-id="fb854-108">これは、ブロッキング操作を含む空のページで、新しい領域の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb854-108">This is a blocking operation that involves filling the new space with empty pages.</span></span> <span data-ttu-id="fb854-109">SQL Server on Windows は、「ファイルの瞬時初期化」をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fb854-109">SQL Server on Windows supports “instant file initialization.”</span></span> <span data-ttu-id="fb854-110">これは、ファイルの拡張操作のパフォーマンスに与える影響を大幅に減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="fb854-110">This can greatly reduce the performance impact of a file growth operation.</span></span> <span data-ttu-id="fb854-111">詳細については、「 [データベース ファイルの初期化](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb854-111">For more information, see [Database File Initialization](https://docs.microsoft.com/sql/relational-databases/databases/database-instant-file-initialization).</span></span> <span data-ttu-id="fb854-112">このトピックでは、ファイルの瞬時初期化を有効にする際に必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb854-112">This topic outlines the steps that must be taken to enable instant file initialization.</span></span>  
  
## <a name="enabling-instant-file-initialization"></a><span data-ttu-id="fb854-113">ファイルの瞬時初期化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fb854-113">Enabling Instant File Initialization</span></span>  
 <span data-ttu-id="fb854-114">インスタント有効にする方法の手順は、初期化ファイルを参照してください[データベース ファイルの初期化](https://docs.microsoft.com/en-us/sql/relational-databases/databases/database-instant-file-initialization)です。</span><span class="sxs-lookup"><span data-stu-id="fb854-114">For steps on enabling instant file initialization, see [Database File Initialization](https://docs.microsoft.com/en-us/sql/relational-databases/databases/database-instant-file-initialization).</span></span> <span data-ttu-id="fb854-115">ファイル グループを作成すると、適切なファイル グループに BizTalk Server データベース テーブル、インデックス、およびログ ファイルを移動する、推奨事項に従って"付録 B-推奨される BizTalk Server データベース構成で"で、 ["BizTalk Serverホワイト ペーパーのデータベースの最適化"](http://go.microsoft.com/fwlink/?LinkID=101578)です。</span><span class="sxs-lookup"><span data-stu-id="fb854-115">For creating file groups and moving the BizTalk Server database tables, indexes, and log files into the appropriate file groups, follow the recommendations in "Appendix B - Recommended BizTalk Server Database Configuration" in the ["BizTalk Server Database Optimization" white paper](http://go.microsoft.com/fwlink/?LinkID=101578).</span></span> <span data-ttu-id="fb854-116">理想的にはファイル グループをサポートするファイルのサイズを事前に割り当てられるし、可能な場合は、静的なサイズに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb854-116">Ideally the size of files supporting the file groups should be pre-allocated and if possible, set to a static size.</span></span>  
  
 <span data-ttu-id="fb854-117">ファイルを構成し、システムが新しい静的なサイズが決定的確立されていない場合は、**自動拡張を有効にする**オプションし、ファイル拡張を指定**メガバイト単位で**です。</span><span class="sxs-lookup"><span data-stu-id="fb854-117">If the system is new and the static sizes have not been definitively established, then configure files with the **Enable Autogrowth** option and specify file growth **In Megabytes**.</span></span> <span data-ttu-id="fb854-118">拡張増分値を超える 100 MB (サイズの大きいファイル)、10 MB (中規模ファイル用)、または 1 MB (小さなファイル用)、通常場合があります。</span><span class="sxs-lookup"><span data-stu-id="fb854-118">The growth increment should generally be no larger than 100 MB (for large files), 10 MB (for medium-sized files), or 1 MB (for small files).</span></span>