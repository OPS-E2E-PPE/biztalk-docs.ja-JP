---
title: 関数名とレコード Types1 プロシージャに対する操作 |Microsoft ドキュメント
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
ms.openlocfilehash: 43974d1c392a357b9781ff7f6fae5286e282513a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216082"
---
# <a name="operations-on-functions-and-procedures-with-record-types"></a><span data-ttu-id="11e14-102">関数およびレコードの種類のプロシージャでの操作</span><span class="sxs-lookup"><span data-stu-id="11e14-102">Operations on Functions and Procedures with RECORD Types</span></span>
<span data-ttu-id="11e14-103">Oracle のレコードの種類は、PL/SQL 関数およびプロシージャに渡されるパラメーターで階層的な情報を表すために使用されます。</span><span class="sxs-lookup"><span data-stu-id="11e14-103">Oracle RECORD types are used to represent hierarchical information in parameters passed to PL/SQL functions and procedures.</span></span> <span data-ttu-id="11e14-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]複雑な XML 型としてレコードの種類を表示します。</span><span class="sxs-lookup"><span data-stu-id="11e14-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces RECORD types as complex XML types.</span></span> 

## <a name="supported-record-types"></a><span data-ttu-id="11e14-105">サポートされているレコードの種類</span><span class="sxs-lookup"><span data-stu-id="11e14-105">Supported RECORD types</span></span>
<span data-ttu-id="11e14-106">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]次の種類のレコードの種類をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="11e14-106">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] supports the following kinds of RECORD types:</span></span>  
  
-   <span data-ttu-id="11e14-107">ストアド プロシージャおよび関数では、テーブル %rowtype パラメーターとして宣言されているレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="11e14-107">RECORD types that are declared as TABLE%ROWTYPE parameters in stored procedures and functions.</span></span>  
  
-   <span data-ttu-id="11e14-108">PL/SQL パッケージ内のレコードの型パラメーターとして宣言されているレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="11e14-108">RECORD types that are declared as TYPE of RECORD parameters in PL/SQL packages.</span></span> <span data-ttu-id="11e14-109">たとえば、型 rec_type1 は RECORD(name varchar2(100), age number(3));</span><span class="sxs-lookup"><span data-stu-id="11e14-109">For example, TYPE rec_type1 IS RECORD(name varchar2(100), age number(3));</span></span>  
  
-   <span data-ttu-id="11e14-110">入れ子になったレコードを含むレコードの種類。</span><span class="sxs-lookup"><span data-stu-id="11e14-110">RECORD types that contain nested records.</span></span>  
  
-   <span data-ttu-id="11e14-111">レコードに表示される型として、OUT、またはプロシージャまたは関数への OUT パラメーターです。</span><span class="sxs-lookup"><span data-stu-id="11e14-111">RECORD types that appear as IN, OUT, or IN OUT parameters to procedures or functions.</span></span>  
  
-   <span data-ttu-id="11e14-112">関数の戻り値は、レコードの種類。</span><span class="sxs-lookup"><span data-stu-id="11e14-112">RECORD types that are RETURN values of functions.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11e14-113">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]レコードのメンバーとして BFILE 型をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="11e14-113">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] does not support BFILE types as RECORD members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e14-114">参照</span><span class="sxs-lookup"><span data-stu-id="11e14-114">See Also</span></span>  
 <span data-ttu-id="11e14-115">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="11e14-115">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>