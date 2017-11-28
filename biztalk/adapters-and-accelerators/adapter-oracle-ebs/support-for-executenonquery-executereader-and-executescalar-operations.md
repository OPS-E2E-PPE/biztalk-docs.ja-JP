---
title: "ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afdd1a5b-2a6b-48b8-a659-afd81f43f34b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40bad547627669bb22a6b32f05d96c6c7b2f68c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="da7db-102">ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のサポート</span><span class="sxs-lookup"><span data-stu-id="da7db-102">Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>
<span data-ttu-id="da7db-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]ルート レベルの次の送信操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="da7db-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes the following outbound operations at the root level:</span></span>  
  
-   <span data-ttu-id="da7db-104">**ExecuteNonQuery**: この操作を使用すると、複数の結果セットを取得する場合に、Oracle E-business Suite での任意の SQL ステートメントまたは PL/SQL ブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="da7db-104">**ExecuteNonQuery**: Use this operation to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite if you want to return multiple result sets.</span></span> <span data-ttu-id="da7db-105">この関数の入力パラメーターには、文字列パラメーター (PL/SQL ブロック全体を実行する) と (OutRefCursorNames) の文字列の配列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="da7db-105">The input parameters of this function include a string parameter (the entire PL/SQL block to be executed) and an array of strings (OutRefCursorNames).</span></span> <span data-ttu-id="da7db-106">OutRefCursorNames で指定した各文字列の値は、出力と同じ名前を持つ REF CURSOR を返す PL/SQL ブロックの REF CURSOR のパラメーター名と見なされます。</span><span class="sxs-lookup"><span data-stu-id="da7db-106">Each string value specified in OutRefCursorNames is assumed to be the parameter name of an output REF CURSOR with the PL/SQL block returning REF CURSORS with the same names.</span></span> <span data-ttu-id="da7db-107">この関数は、データセットの配列をある OUT パラメーター (OutRefCursors) も受け取ります。</span><span class="sxs-lookup"><span data-stu-id="da7db-107">This function also takes an OUT parameter (OutRefCursors), which is an array of DataSets.</span></span> <span data-ttu-id="da7db-108">データセットについては、Oracle のマニュアルを参照してください。 [http://go.microsoft.com/fwlink/?LinkId=124538](http://go.microsoft.com/fwlink/?LinkId=124538)です。</span><span class="sxs-lookup"><span data-stu-id="da7db-108">For information about DataSet, consult the Oracle documentation at [http://go.microsoft.com/fwlink/?LinkId=124538](http://go.microsoft.com/fwlink/?LinkId=124538).</span></span> <span data-ttu-id="da7db-109">この操作の戻り値は整数データ型の影響を受けた行の数を示します。</span><span class="sxs-lookup"><span data-stu-id="da7db-109">The return value of this operation is of integer data type, and indicates the number of affected rows.</span></span>  
  
-   <span data-ttu-id="da7db-110">**ExecuteReader**: この操作を使用して、結果セットをデータセットとして指定する場合、Oracle E-business Suite で任意の SQL ステートメントや PL/SQL ブロックがあるを実行します。</span><span class="sxs-lookup"><span data-stu-id="da7db-110">**ExecuteReader**: Use this operation to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite if you want the result set to be returned as DataSet.</span></span> <span data-ttu-id="da7db-111">この操作は、入力として文字列パラメーターを受け取り、データセットを返します。</span><span class="sxs-lookup"><span data-stu-id="da7db-111">This operation takes a string parameter as input, and returns a DataSet.</span></span>  
  
-   <span data-ttu-id="da7db-112">**ExecuteScalar**: この操作を使用して返される値を 1 つだけの場合に、Oracle E-business Suite で、任意の SQL ステートメントまたは PL/SQL ブロックを実行します。</span><span class="sxs-lookup"><span data-stu-id="da7db-112">**ExecuteScalar**: Use this operation to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite if you want only one value to be returned.</span></span> <span data-ttu-id="da7db-113">戻り値が結果セットの場合は、最初の行の最初の列の値だけが XML 文字列の形式で返されます。</span><span class="sxs-lookup"><span data-stu-id="da7db-113">If the return value is a result set, only the value in the first column of the first row is returned in a XML string format.</span></span>  
  
> [!NOTE]
>  -   <span data-ttu-id="da7db-114">ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作はユーザー定義型 (Udt) のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="da7db-114">The ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations are not supported for the User Defined Types (UDTs).</span></span>  
> -   <span data-ttu-id="da7db-115">内の ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作用のアプリケーションのコンテキストを設定することもできます。[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="da7db-115">You can also set the applications context for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="da7db-116">Oracle E-business Suite (インターフェイス テーブル、ビューのインターフェイス、同時実行プログラムまたは要求内の成果物のターゲットが、操作のいずれかの場合に、ExecuteNonQuery、ExecuteReader、および ExecuteScalar 操作のアプリケーション コンテキストを設定する必要が設定します)。</span><span class="sxs-lookup"><span data-stu-id="da7db-116">It is mandatory to set the applications context for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations if any of the operation is targeted on an artifact in Oracle E-Business Suite (interface table, interface view, concurrent programs or request sets).</span></span> <span data-ttu-id="da7db-117">アプリケーションのコンテキスト、およびように設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。</span><span class="sxs-lookup"><span data-stu-id="da7db-117">For information about applications context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da7db-118">参照</span><span class="sxs-lookup"><span data-stu-id="da7db-118">See Also</span></span>  
 <span data-ttu-id="da7db-119">[どのような操作をアダプターであるを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="da7db-119">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>