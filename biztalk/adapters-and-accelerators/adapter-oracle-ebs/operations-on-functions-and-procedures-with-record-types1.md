---
title: レコード Types1 で関数とプロシージャに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afc1c84f-2e36-493c-9ea8-4bc2248331db
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b7d4f392e863dd8966f5c011abfd6e602f2514c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006435"
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a><span data-ttu-id="003f8-102">関数とレコードの種類を使用したプロシージャに対する操作</span><span class="sxs-lookup"><span data-stu-id="003f8-102">Operations on Functions and Procedures with RECORD Types</span></span>
<span data-ttu-id="003f8-103">Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="003f8-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="003f8-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]サーフェスの複雑な XML 型としてレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="003f8-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> 

## <a name="supported-record-types"></a><span data-ttu-id="003f8-105">サポートされているレコードの種類</span><span class="sxs-lookup"><span data-stu-id="003f8-105">Supported RECORD types</span></span>
<span data-ttu-id="003f8-106">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]次の種類のレコードの種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="003f8-106">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports the following kinds of RECORD types:</span></span>  
  
- <span data-ttu-id="003f8-107">ストアド プロシージャおよび関数でテーブル %rowtype パラメーターとして宣言されているレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="003f8-107">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
- <span data-ttu-id="003f8-108">PL/SQL パッケージ内のレコードの型パラメーターとして宣言されているレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="003f8-108">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages.</span></span> <span data-ttu-id="003f8-109">たとえば、rec_type1 は RECORD(name varchar2(100), age number(3)); を入力します。</span><span class="sxs-lookup"><span data-stu-id="003f8-109">For example, TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));</span></span>  
  
- <span data-ttu-id="003f8-110">入れ子になったレコードを含むレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="003f8-110">RECORD types that contain nested records.</span></span>  
  
- <span data-ttu-id="003f8-111">OUT、IN として表示されるレコードの種類またはプロシージャまたは関数への OUT パラメーター。</span><span class="sxs-lookup"><span data-stu-id="003f8-111">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
- <span data-ttu-id="003f8-112">関数の戻り値であるレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="003f8-112">RECORD types that are RETURN values of functions.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="003f8-113">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]レコードのメンバーとして BFILE 型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="003f8-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003f8-114">参照</span><span class="sxs-lookup"><span data-stu-id="003f8-114">See Also</span></span>  
 <span data-ttu-id="003f8-115">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="003f8-115">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>