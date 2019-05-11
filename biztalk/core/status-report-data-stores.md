---
title: 状態レポート データ ストア |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6cd40ce8-1ac6-43b4-9cef-7cd045e8893c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0cb1d8d2a85cc88364da5bb43131213903b37d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392877"
---
# <a name="status-report-data-stores"></a><span data-ttu-id="fcb21-102">状態レポート データ ストア</span><span class="sxs-lookup"><span data-stu-id="fcb21-102">Status Report Data Stores</span></span>
<span data-ttu-id="fcb21-103">状態レポート追跡データは、BAM プライマリ インポート データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="fcb21-103">Status reporting tracking data is stored in the BAM Primary Import database.</span></span> <span data-ttu-id="fcb21-104">このデータベース内のテーブルの数は、以降で dbo.bam_AS2、dbo.bam.batching、dbo.bam.InterchangeStatusActivity、およびその他のユーザー テーブルを含む EDI および AS2 のメッセージ データに使用されます。</span><span class="sxs-lookup"><span data-stu-id="fcb21-104">A number of tables in this database are used for EDI and AS2 message data, including tables starting with dbo.bam_AS2, dbo.bam.batching, dbo.bam.InterchangeStatusActivity, and others.</span></span> <span data-ttu-id="fcb21-105">状態データは、EDI レポートが無効になっている場合でも、プライマリ インポートに格納されます。</span><span class="sxs-lookup"><span data-stu-id="fcb21-105">Status data is stored in the Primary Import even if EDI reporting is disabled.</span></span> <span data-ttu-id="fcb21-106">表示と、状態レポート UI の状態レポートが有効な場合にこのデータを照会するのみなります。</span><span class="sxs-lookup"><span data-stu-id="fcb21-106">You will only be to view and query this data in the status reporting UI if status reporting is activated.</span></span>  
  
 <span data-ttu-id="fcb21-107">否認不可のために、メッセージ データのストレージを有効にした場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk 追跡データベース (BizTalkDTADb) の EDI メッセージ コンテンツ テーブルに EDI または AS2 データを格納します。</span><span class="sxs-lookup"><span data-stu-id="fcb21-107">If you enable storage of message data for non-repudiation purposes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the EDI and/or AS2 data in the EDI Message Content table of the BizTalk tracking database (BizTalkDTADb).</span></span> <span data-ttu-id="fcb21-108">メッセージの内容、ペイロードの詳細を表示するためのストレージを有効にした場合 (選択して、**メッセージ ペイロードを格納するレポートの**アグリーメントのプロパティ、**全般プロパティ**のページ**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス)、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]このテーブルにトランザクション セットを格納もされます。</span><span class="sxs-lookup"><span data-stu-id="fcb21-108">If you enable storage of message contents for viewing details of the payload (by selecting the **Store message payload for reporting** agreement property in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box), [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also store the transaction sets in this table.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="fcb21-109">アーカイブして、BAM プライマリ インポート データベースと BizTalkDTADb データベースからデータを削除します。</span><span class="sxs-lookup"><span data-stu-id="fcb21-109">archives and purges data from the BAM Primary Import and BizTalkDTADb databases.</span></span> <span data-ttu-id="fcb21-110">データベースのテーブルに定期的なスケジュールに従ってクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="fcb21-110">The tables in the databases are cleaned out according to a regular schedule.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fcb21-111">BAM プライマリ インポート データベースと DTA DB データベースは同期していない場合、それぞれにアーカイブするためのさまざまな間隔で可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fcb21-111">The BAM Primary Import and DTA DB databases could be out of synch if each has a different interval for archiving.</span></span>  
  
 <span data-ttu-id="fcb21-112">EDI および AS2 状態レポートと、パフォーマンスに影響を与えるをがあります。</span><span class="sxs-lookup"><span data-stu-id="fcb21-112">EDI and AS2 status reporting may have an impact upon performance.</span></span> <span data-ttu-id="fcb21-113">詳細についてを参照してください「のパフォーマンスに関する考慮事項の EDI および AS2 状態レポート」 [EDI および AS2 のパフォーマンスに関する既知の問題](../core/known-issues-with-edi-and-as2-performance.md)します。</span><span class="sxs-lookup"><span data-stu-id="fcb21-113">For more information, see "Performance Considerations for EDI and AS2 Status Reporting" in [Known Issues with EDI and AS2 Performance](../core/known-issues-with-edi-and-as2-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcb21-114">参照</span><span class="sxs-lookup"><span data-stu-id="fcb21-114">See Also</span></span>  
 [<span data-ttu-id="fcb21-115">EDI および AS2 状態レポートのデータ格納方法</span><span class="sxs-lookup"><span data-stu-id="fcb21-115">How Data Is Stored for EDI and AS2 Status Reports</span></span>](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)