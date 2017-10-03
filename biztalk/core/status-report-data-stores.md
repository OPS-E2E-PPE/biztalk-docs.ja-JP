---
title: "状態レポート データ ストア |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cd40ce8-1ac6-43b4-9cef-7cd045e8893c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da876f1151b641216cf9613f6830ed84049da83d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="status-report-data-stores"></a><span data-ttu-id="17f69-102">状態レポート データ ストア</span><span class="sxs-lookup"><span data-stu-id="17f69-102">Status Report Data Stores</span></span>
<span data-ttu-id="17f69-103">状態レポート追跡データは、BAM プライマリ インポート データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="17f69-103">Status reporting tracking data is stored in the BAM Primary Import database.</span></span> <span data-ttu-id="17f69-104">このデータベースの多数のテーブル (dbo.bam_AS2、dbo.bam.batching、dbo.bam.InterchangeStatusActivity などで始まるテーブルを含む) は、EDI および AS2 メッセージ データに使用されます。</span><span class="sxs-lookup"><span data-stu-id="17f69-104">A number of tables in this database are used for EDI and AS2 message data, including tables starting with dbo.bam_AS2, dbo.bam.batching, dbo.bam.InterchangeStatusActivity, and others.</span></span> <span data-ttu-id="17f69-105">EDI レポートが無効になっている場合でも、状態データはプライマリ インポートに格納されます。</span><span class="sxs-lookup"><span data-stu-id="17f69-105">Status data is stored in the Primary Import even if EDI reporting is disabled.</span></span> <span data-ttu-id="17f69-106">状態レポートがアクティブになっている場合、実行できるのは、状態レポート内のこのデータの表示と照会のみです。</span><span class="sxs-lookup"><span data-stu-id="17f69-106">You will only be to view and query this data in the status reporting UI if status reporting is activated.</span></span>  
  
 <span data-ttu-id="17f69-107">否認不可を目的とするメッセージ データを格納できるようにすると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は BizTalk 追跡データベース (BizTalkDTADb) の EDI メッセージ コンテンツ テーブルに EDI または AS2 データを格納します。</span><span class="sxs-lookup"><span data-stu-id="17f69-107">If you enable storage of message data for non-repudiation purposes, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store the EDI and/or AS2 data in the EDI Message Content table of the BizTalk tracking database (BizTalkDTADb).</span></span> <span data-ttu-id="17f69-108">ペイロードの詳細を表示するメッセージの内容の記憶域を有効にした場合 (を選択して、 **reporting 用メッセージ ペイロードを格納**アグリーメント プロパティで、**全般プロパティ**のページ**全般** タブで、**アグリーメントのプロパティ** ダイアログ ボックス)、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]もこのテーブルにトランザクション セットを保存します。</span><span class="sxs-lookup"><span data-stu-id="17f69-108">If you enable storage of message contents for viewing details of the payload (by selecting the **Store message payload for reporting** agreement property in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box), [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will also store the transaction sets in this table.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="17f69-109"> は、BAM プライマリ インポート データベースと BizTalkDTADb データベースからデータをアーカイブして削除します。</span><span class="sxs-lookup"><span data-stu-id="17f69-109"> archives and purges data from the BAM Primary Import and BizTalkDTADb databases.</span></span> <span data-ttu-id="17f69-110">データベースのテーブルは、定期的にクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="17f69-110">The tables in the databases are cleaned out according to a regular schedule.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17f69-111">BAM プライマリ インポート データベースと DTA DB データベースは、それぞれのアーカイブ間隔が異なる場合、同期しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17f69-111">The BAM Primary Import and DTA DB databases could be out of synch if each has a different interval for archiving.</span></span>  
  
 <span data-ttu-id="17f69-112">EDI および AS2 状態レポートは、パフォーマンスに影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17f69-112">EDI and AS2 status reporting may have an impact upon performance.</span></span> <span data-ttu-id="17f69-113">詳細についてを参照してください「のパフォーマンスに関する考慮事項の EDI および AS2 状態レポート」 [EDI と AS2 のパフォーマンスの既知の問題](../core/known-issues-with-edi-and-as2-performance.md)です。</span><span class="sxs-lookup"><span data-stu-id="17f69-113">For more information, see "Performance Considerations for EDI and AS2 Status Reporting" in [Known Issues with EDI and AS2 Performance](../core/known-issues-with-edi-and-as2-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f69-114">参照</span><span class="sxs-lookup"><span data-stu-id="17f69-114">See Also</span></span>  
 [<span data-ttu-id="17f69-115">EDI および AS2 状態レポートのデータを格納する方法</span><span class="sxs-lookup"><span data-stu-id="17f69-115">How Data Is Stored for EDI and AS2 Status Reports</span></span>](../core/how-data-is-stored-for-edi-and-as2-status-reports.md)