---
title: ExecuteNonQuery、ExecuteReader、ExecuteScalar 操作のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: afdd1a5b-2a6b-48b8-a659-afd81f43f34b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30669e4f055e6a9783b87d78e774944370421b70
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374527"
---
# <a name="support-for-executenonquery-executereader-and-executescalar-operations"></a><span data-ttu-id="f2c30-102">ExecuteNonQuery、ExecuteReader、executescalar 操作をサポートします。</span><span class="sxs-lookup"><span data-stu-id="f2c30-102">Support for ExecuteNonQuery, ExecuteReader, and ExecuteScalar Operations</span></span>
<span data-ttu-id="f2c30-103">[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]ルート レベルで次の送信操作を公開します。</span><span class="sxs-lookup"><span data-stu-id="f2c30-103">The [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] exposes the following outbound operations at the root level:</span></span>  
  
-   <span data-ttu-id="f2c30-104">**ExecuteNonQuery**:複数の結果セットを取得する場合に、Oracle E-business Suite で、任意の SQL ステートメントまたは PL/SQL ブロックを実行するのにには、この操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2c30-104">**ExecuteNonQuery**: Use this operation to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite if you want to return multiple result sets.</span></span> <span data-ttu-id="f2c30-105">この関数の入力パラメーターには、文字列パラメーター (実行全体の PL/SQL ブロック) および (OutRefCursorNames) 文字列の配列が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2c30-105">The input parameters of this function include a string parameter (the entire PL/SQL block to be executed) and an array of strings (OutRefCursorNames).</span></span> <span data-ttu-id="f2c30-106">OutRefCursorNames で指定した各文字列値は、出力と同じ名前を持つ REF CURSOR を返す PL/SQL ブロックの REF CURSOR のパラメーター名と見なされます。</span><span class="sxs-lookup"><span data-stu-id="f2c30-106">Each string value specified in OutRefCursorNames is assumed to be the parameter name of an output REF CURSOR with the PL/SQL block returning REF CURSORS with the same names.</span></span> <span data-ttu-id="f2c30-107">この関数は、データセットの配列である OUT パラメーター (OutRefCursors) も受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f2c30-107">This function also takes an OUT parameter (OutRefCursors), which is an array of DataSets.</span></span> <span data-ttu-id="f2c30-108">データセットの詳細についてでの Oracle のマニュアルを参照してください。 [ http://go.microsoft.com/fwlink/?LinkId=124538](http://go.microsoft.com/fwlink/?LinkId=124538)します。</span><span class="sxs-lookup"><span data-stu-id="f2c30-108">For information about DataSet, consult the Oracle documentation at [http://go.microsoft.com/fwlink/?LinkId=124538](http://go.microsoft.com/fwlink/?LinkId=124538).</span></span> <span data-ttu-id="f2c30-109">この操作の戻り値が整数データ型の影響を受けた行の数を示します。</span><span class="sxs-lookup"><span data-stu-id="f2c30-109">The return value of this operation is of integer data type, and indicates the number of affected rows.</span></span>  
  
-   <span data-ttu-id="f2c30-110">**ExecuteReader**:結果セットをデータセットとして指定する場合に、Oracle E-business Suite で、任意の SQL ステートメントまたは PL/SQL ブロックを実行するのにには、この操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2c30-110">**ExecuteReader**: Use this operation to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite if you want the result set to be returned as DataSet.</span></span> <span data-ttu-id="f2c30-111">この操作は、入力として文字列パラメーターを受け取り、データセットを返します。</span><span class="sxs-lookup"><span data-stu-id="f2c30-111">This operation takes a string parameter as input, and returns a DataSet.</span></span>  
  
-   <span data-ttu-id="f2c30-112">**ExecuteScalar**:返される値の 1 つだけの場合、Oracle E-business Suite で、任意の SQL ステートメントまたは PL/SQL ブロックを実行するのにには、この操作を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2c30-112">**ExecuteScalar**: Use this operation to execute any arbitrary SQL statements or PL/SQL blocks in Oracle E-Business Suite if you want only one value to be returned.</span></span> <span data-ttu-id="f2c30-113">結果セットを戻り値には、XML 文字列の形式で、最初の行の最初の列の値だけが返されます。</span><span class="sxs-lookup"><span data-stu-id="f2c30-113">If the return value is a result set, only the value in the first column of the first row is returned in a XML string format.</span></span>  
  
> [!NOTE]
> - <span data-ttu-id="f2c30-114">ExecuteNonQuery、ExecuteReader、executescalar 操作はユーザー定義型 (Udt) のサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f2c30-114">The ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations are not supported for the User Defined Types (UDTs).</span></span>  
>   - <span data-ttu-id="f2c30-115">ExecuteNonQuery、ExecuteReader、executescalar 操作のアプリケーションのコンテキストを設定することもできます。[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f2c30-115">You can also set the applications context for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations in [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="f2c30-116">Oracle E-business Suite (インターフェイス テーブル、インターフェイス ビュー、同時実行プログラムまたは要求内のアイテムに対象が、操作のいずれかの場合は、ExecuteNonQuery、ExecuteReader、executescalar 操作のアプリケーション コンテキストを設定する必要があります。セットの場合)。</span><span class="sxs-lookup"><span data-stu-id="f2c30-116">It is mandatory to set the applications context for the ExecuteNonQuery, ExecuteReader, and ExecuteScalar operations if any of the operation is targeted on an artifact in Oracle E-Business Suite (interface table, interface view, concurrent programs or request sets).</span></span> <span data-ttu-id="f2c30-117">アプリケーションのコンテキスト、および設定する方法については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。</span><span class="sxs-lookup"><span data-stu-id="f2c30-117">For information about applications context, and how to set it, see [Set Application Context](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2c30-118">参照</span><span class="sxs-lookup"><span data-stu-id="f2c30-118">See Also</span></span>  
 <span data-ttu-id="f2c30-119">[どのような操作は、アダプターを使用して実行しますか?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="f2c30-119">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>