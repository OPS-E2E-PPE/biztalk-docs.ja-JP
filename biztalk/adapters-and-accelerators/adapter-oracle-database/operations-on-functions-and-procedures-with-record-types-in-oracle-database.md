---
title: Oracle データベースのレコードの種類で関数とプロシージャに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- RECORD type
ms.assetid: 28ecb76c-de82-43df-83cc-917c482417b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 393944d0f01e1ebb4010f3963337b1f2182e7623
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376331"
---
# <a name="operations-on-functions-and-procedures-with-record-types-in-oracle-database"></a><span data-ttu-id="fb90c-102">Oracle データベースのレコードの種類で関数とプロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="fb90c-102">Operations on Functions and Procedures with RECORD Types in Oracle Database</span></span>
<span data-ttu-id="fb90c-103">Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb90c-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="fb90c-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの複雑な XML 型としてレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="fb90c-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> <span data-ttu-id="fb90c-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]次の種類のレコードの種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fb90c-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the following kinds of RECORD types:</span></span>  
  
- <span data-ttu-id="fb90c-106">ストアド プロシージャおよび関数でテーブル %rowtype パラメーターとして宣言されているレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="fb90c-106">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
- <span data-ttu-id="fb90c-107">たとえば、PL/SQL パッケージ内のレコードの型パラメーターとして宣言されているレコードの種類の入力 rec_type1 は RECORD(name varchar2(100), age number(3));</span><span class="sxs-lookup"><span data-stu-id="fb90c-107">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages for example, TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));</span></span>  
  
- <span data-ttu-id="fb90c-108">入れ子になったレコードを含むレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="fb90c-108">RECORD types that contain nested records.</span></span>  
  
- <span data-ttu-id="fb90c-109">OUT、IN として表示されるレコードの種類またはプロシージャまたは関数への OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="fb90c-109">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
- <span data-ttu-id="fb90c-110">関数の戻り値であるレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="fb90c-110">RECORD types that are RETURN values of functions.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="fb90c-111">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]レコードのメンバーとして BFILE 型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fb90c-111">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
  <span data-ttu-id="fb90c-112">詳細については。</span><span class="sxs-lookup"><span data-stu-id="fb90c-112">For information about:</span></span>  
  
- <span data-ttu-id="fb90c-113">関数または WCF サービス モデルを使用してレコードの種類に関連するプロシージャを呼び出しを参照してください[実行の操作を使用してレコードの種類、WCF サービス モデルを使用して Oracle データベース](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md)します。</span><span class="sxs-lookup"><span data-stu-id="fb90c-113">Invoking a function or procedure involving RECORD types using the WCF service model, see [Run Operations Using RECORD Types in Oracle Database using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/using-record-types-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
- <span data-ttu-id="fb90c-114">関数またはプロシージャのレコードに関連する型を使用して呼び出す[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を参照してください[を使用して BizTalk Server でのレコードの種類で呼び出す関数とプロシージャ](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="fb90c-114">Invoking a function or procedure involving RECORD types using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], see [Invoke Functions and Procedures with RECORD Types by Using BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/run-functions-and-procedures-with-record-types-in-oracle-db-with-biztalk-server.md).</span></span>  
  
- <span data-ttu-id="fb90c-115">レコードの XML 構造の種類でサポートされている、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[レコードの種類のメッセージ スキーマ](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md)します。</span><span class="sxs-lookup"><span data-stu-id="fb90c-115">XML structure for RECORD types as supported by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Message Schemas for RECORD Types](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-record-types.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb90c-116">参照</span><span class="sxs-lookup"><span data-stu-id="fb90c-116">See Also</span></span>  
 <span data-ttu-id="fb90c-117">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="fb90c-117">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>