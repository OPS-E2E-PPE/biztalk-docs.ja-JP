---
title: BizTalk adapter for SQL Server の制限事項 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a19b109-a6b7-452f-a544-48627fa52f36
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5a80990a9e3f417b64a06d8823300d53b2c4f3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222682"
---
# <a name="limitations-of-biztalk-adapter-for-sql-server"></a><span data-ttu-id="c06e2-102">BizTalk adapter for SQL Server の制限事項</span><span class="sxs-lookup"><span data-stu-id="c06e2-102">Limitations of BizTalk Adapter for SQL Server</span></span>
<span data-ttu-id="c06e2-103">次はの既知の制限[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="c06e2-103">The following are known limitations for [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]:</span></span>  
  
-   <span data-ttu-id="c06e2-104">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]は SQL Server データベースに作成されたシノニムをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="c06e2-104">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support synonyms created in the SQL Server database.</span></span> <span data-ttu-id="c06e2-105">SQL Server でのシノニムについて、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=120111](http://go.microsoft.com/fwlink/?LinkId=120111)です。</span><span class="sxs-lookup"><span data-stu-id="c06e2-105">For information about synonyms in SQL Server, see [http://go.microsoft.com/fwlink/?LinkId=120111](http://go.microsoft.com/fwlink/?LinkId=120111).</span></span>  
  
-   <span data-ttu-id="c06e2-106">実行するコンピューターのシステム時刻を変更するかどうか、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ホスト、時間が自動的に更新されませんで、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ホストします。</span><span class="sxs-lookup"><span data-stu-id="c06e2-106">If you change the system time of the computer running the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host, the time is not updated automatically in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] host.</span></span> <span data-ttu-id="c06e2-107">受信ポートを使用する受信操作の不適切な動作する可能性が[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c06e2-107">This could lead to incorrect behavior of the inbound operations that use the receive port of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="c06e2-108">この問題を回避するを実行するコンピューターのシステム時刻を変更した後、受信ポートを持つホスト インスタンスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c06e2-108">As a workaround, you must restart the host instance that has a receive port after you have changed the system time of the computer running it.</span></span>  
  
-   <span data-ttu-id="c06e2-109">ストアド プロシージャのパラメーター名が 127 以上の文字が含まれている場合は、ストアド プロシージャを使用して、実行することはできません、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="c06e2-109">If a parameter name in a stored procedure contains 127 or more characters, you cannot execute the stored procedure using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="c06e2-110">これは、ADO.NET の制限のためです。</span><span class="sxs-lookup"><span data-stu-id="c06e2-110">This is due to the limitation of ADO.NET.</span></span>  
  
-   <span data-ttu-id="c06e2-111">WSDL、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]プロキシに変換すると、生成された場合、System.DateTime として DateTimeOffset 列を公開します。</span><span class="sxs-lookup"><span data-stu-id="c06e2-111">The WSDL the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] generates, when converted to a proxy, exposes the DateTimeOffset column as System.DateTime.</span></span> <span data-ttu-id="c06e2-112">このデータ型は、タイム ゾーン情報を格納できません。</span><span class="sxs-lookup"><span data-stu-id="c06e2-112">This data type cannot store time zone information.</span></span> <span data-ttu-id="c06e2-113">結果として、アダプターの送信プロキシに任意の日付/時刻値は、.NET アプリケーションでのローカル時刻に変換されます。</span><span class="sxs-lookup"><span data-stu-id="c06e2-113">As a consequence, any date/time value the adapter sends to the proxy will be converted into local time in the .NET application.</span></span> <span data-ttu-id="c06e2-114">タイム ゾーン情報を保持する場合は、System.DateTime ではなく、文字列型を使用するプロキシのインターフェイスを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c06e2-114">If you wish to keep the time zone information, you must change the interface of your proxy to use the String type instead of System.DateTime.</span></span> <span data-ttu-id="c06e2-115">XmlConvert.ToDateTimeOffset を使用してのタイム ゾーン情報を格納する、Sytstem.DateTimeOffset オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c06e2-115">Then, use XmlConvert.ToDateTimeOffset to create a Sytstem.DateTimeOffset object, which can store the timezone information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c06e2-116">参照</span><span class="sxs-lookup"><span data-stu-id="c06e2-116">See Also</span></span>  
 [<span data-ttu-id="c06e2-117">SQL Server の BizTalk アダプターを理解します。</span><span class="sxs-lookup"><span data-stu-id="c06e2-117">UNderstand BizTalk Adapter for SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)