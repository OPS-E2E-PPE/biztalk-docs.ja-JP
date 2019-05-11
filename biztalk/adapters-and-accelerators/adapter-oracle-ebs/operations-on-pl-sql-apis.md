---
title: PL-SQL Api の操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d47b894d-1047-48ed-8f8c-865c343a12db
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c65a1a6313b70b03894c2d4adc41d7679d71b82c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375326"
---
# <a name="operations-on-plsql-apis"></a><span data-ttu-id="3edba-102">PL/SQL Api に対する操作</span><span class="sxs-lookup"><span data-stu-id="3edba-102">Operations on PL/SQL APIs</span></span>
<span data-ttu-id="3edba-103">Oracle E-business Suite では、パッケージ化された関数およびストアド プロシージャの形式で PL/SQL Api のセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="3edba-103">Oracle E-Business Suite provides a set of PL/SQL APIs in the form of packaged functions and stored procedures.</span></span> <span data-ttu-id="3edba-104">これらのパッケージ化関数とプロシージャでの操作として表示された[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3edba-104">These packaged functions and procedures are surfaced as operations in [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span> 

## <a name="plsql-apis-are-grouped-by-schema-names"></a><span data-ttu-id="3edba-105">PL/SQL Api は、スキーマ名でグループ化されます。</span><span class="sxs-lookup"><span data-stu-id="3edba-105">PL/SQL APIs are grouped by schema names</span></span> 
<span data-ttu-id="3edba-106">PL/SQL Api は、下にあるスキーマ名でグループ化されます、**成果物ベースのビュー**と**ビューのスキーマに基づく**Oracle E-business Suite に接続したときにノード[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3edba-106">The PL/SQL APIs are grouped by schema names under the **Artifact-Based View** and **Schema-Based View** nodes when you connect to Oracle E-Business Suite using [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] or  [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="3edba-107">PL/SQL Api の参照については、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を参照してください[参照、検索、および Oracle E-business 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)します。</span><span class="sxs-lookup"><span data-stu-id="3edba-107">For information about browsing the PL/SQL APIs in the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], see [Browse, Search, and get Metadata for Oracle E-Business Operations](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md).</span></span>  
  
 <span data-ttu-id="3edba-108">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite でのアプリケーションだけでなく、Oracle データベースに関連付けられている PL/SQL Api が表示されます、**成果物ベースのビュー**と**ビューのスキーマに基づく**ノード。</span><span class="sxs-lookup"><span data-stu-id="3edba-108">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] displays the PL/SQL APIs associated with the Oracle database as well as the applications in Oracle E-Business Suite under the **Artifact-Based View** and **Schema-Based View** nodes.</span></span>  
  
## <a name="important-info"></a><span data-ttu-id="3edba-109">重要な情報</span><span class="sxs-lookup"><span data-stu-id="3edba-109">Important info</span></span>
  -   <span data-ttu-id="3edba-110">Oracle E-business Suite でのアプリケーションに関連付けられている PL/SQL Api に対する操作を実行する前に、アプリケーションのコンテキストを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3edba-110">Before you can perform operations on PL/SQL APIs associated with applications in Oracle E-Business Suite, you must set the applications context.</span></span> <span data-ttu-id="3edba-111">アプリケーション コンテキストの設定 (責任、組織、および言語の設定) などのユーザー設定とアーティファクトのアクセス制御を設定して Oracle E-business Suite でセキュリティで保護されたトランザクションを促進するためです。</span><span class="sxs-lookup"><span data-stu-id="3edba-111">This is because setting applications context facilitates secure transactions in Oracle E-Business Suite by setting user preferences (such as responsibility, organization, and language settings) and access control for an artifact.</span></span> <span data-ttu-id="3edba-112">ただし、Oracle データベースに関連付けられた PL/SQL Api のアプリケーションのコンテキストを設定する省略可能です。</span><span class="sxs-lookup"><span data-stu-id="3edba-112">However, it is optional to set the applications context for PL/SQL APIs associated with Oracle database.</span></span> <span data-ttu-id="3edba-113">参照してください[アプリケーション コンテキストを設定する](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="3edba-113">See [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  

- <span data-ttu-id="3edba-114">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle PL/SQL API のパラメーターの既定値が割り当てられているかどうかを確認することはできません。</span><span class="sxs-lookup"><span data-stu-id="3edba-114">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] cannot ascertain whether or not a default value is assigned for a parameter in a PL/SQL API in Oracle.</span></span>  <span data-ttu-id="3edba-115">さらに、アダプターもできない確認パラメーターが必須または Oracle の PL/SQL API では省略可能として定義されているかどうか。</span><span class="sxs-lookup"><span data-stu-id="3edba-115">Moreover, the adapter also cannot ascertain whether a parameter is defined as mandatory or optional in a PL/SQL API in Oracle.</span></span> <span data-ttu-id="3edba-116">アダプターは、オプションのパラメーターとしてすべてのパラメーターを処理し、パラメーターの値が指定されていない場合です。</span><span class="sxs-lookup"><span data-stu-id="3edba-116">The adapter treats every parameter as an optional parameter, and if no value is specified for a parameter that:</span></span>  

  -   <span data-ttu-id="3edba-117">値で指定されている Oracle の既定値を使用し、既定値があります。</span><span class="sxs-lookup"><span data-stu-id="3edba-117">Has a default value specified in Oracle then the default value is used.</span></span>  
  -   <span data-ttu-id="3edba-118">スローされる例外では、Oracle では必須のパラメーターとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="3edba-118">Is defined as a mandatory parameter in Oracle then an exception is thrown.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3edba-119">参照</span><span class="sxs-lookup"><span data-stu-id="3edba-119">See Also</span></span>  
 <span data-ttu-id="3edba-120">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="3edba-120">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>