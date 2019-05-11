---
title: 列が小文字または大文字の値を格納するかどうかを決定する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1edc8332-d8c7-4040-895b-f121fb03df44
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a457ddbde4a6a1dcfa3b4d2c4f818d01dcae009
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373525"
---
# <a name="determining-whether-a-column-stores-lowercase-or-uppercase-values"></a><span data-ttu-id="98012-102">列ストアの小文字または大文字の値かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="98012-102">Determining Whether a Column Stores Lowercase or Uppercase Values</span></span>
<span data-ttu-id="98012-103">このセクションでは、SAP テーブル内の列が小文字または大文字の文字を保存するかどうかを確認するための SAP システムで実行する高度なタスクが一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="98012-103">This section lists high-level tasks to be performed on the SAP system to determine whether a column in an SAP table stores lowercase or uppercase characters.</span></span> <span data-ttu-id="98012-104">このタスクを実行する方法の詳細な手順については、SAP 管理者に問い合わせるか、SAP のマニュアルを参照してくださいする必要があります。</span><span class="sxs-lookup"><span data-stu-id="98012-104">For detailed instructions on how to perform this task you must contact your SAP administrator or refer to SAP documentation.</span></span>  
  
### <a name="to-determine-the-case-of-values-stored-in-a-column"></a><span data-ttu-id="98012-105">列に格納されている値の大文字と小文字を決定するには</span><span class="sxs-lookup"><span data-stu-id="98012-105">To determine the case of values stored in a column</span></span>  
  
1.  <span data-ttu-id="98012-106">SAP GUI を起動します。</span><span class="sxs-lookup"><span data-stu-id="98012-106">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="98012-107">トランザクション SE37 に移動し、DDIF_TABL_GET を実行します。</span><span class="sxs-lookup"><span data-stu-id="98012-107">Go to Transaction SE37 and execute DDIF_TABL_GET.</span></span>  
  
3.  <span data-ttu-id="98012-108">NAME パラメーターの文字の大文字と小文字の情報を決定する列を含むテーブル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="98012-108">For the NAME parameter, specify the table name containing the column for which you want to determine the character case information.</span></span> <span data-ttu-id="98012-109">たとえば、KNA1 です。</span><span class="sxs-lookup"><span data-stu-id="98012-109">For example, KNA1.</span></span>  
  
4.  <span data-ttu-id="98012-110">テーブルの最初のパラメーターは、DD03P_TAB です。</span><span class="sxs-lookup"><span data-stu-id="98012-110">The first table parameter is DD03P_TAB.</span></span> <span data-ttu-id="98012-111">テーブルの行を表示するパラメーターをクリックします。</span><span class="sxs-lookup"><span data-stu-id="98012-111">Click the parameter to see the rows in the table.</span></span> <span data-ttu-id="98012-112">このテーブル内のすべての行が列に対応手順 3. で指定した (KNA1) などの表にします。</span><span class="sxs-lookup"><span data-stu-id="98012-112">Every row in this table corresponds to a column in the table (such as KNA1) you specified in step 3.</span></span>  
  
5.  <span data-ttu-id="98012-113">DD03P_TAB で行ごとに小文字の列の値を探します。</span><span class="sxs-lookup"><span data-stu-id="98012-113">In DD03P_TAB, look for the value in the LOWERCASE column for each row.</span></span> <span data-ttu-id="98012-114">小文字の列の値が 'X'、KNA1) などのテーブルの対応する列の場合は、大文字と小文字の両方を格納できます。</span><span class="sxs-lookup"><span data-stu-id="98012-114">If the value in the LOWERCASE column is 'X', the corresponding column in the table (such as KNA1), can store both lowercase and uppercase characters.</span></span> <span data-ttu-id="98012-115">小文字の列の値が空の場合、対応する列は大文字の文字をのみ格納できます。</span><span class="sxs-lookup"><span data-stu-id="98012-115">If the value in the LOWERCASE column is empty, the corresponding column can only store uppercase characters.</span></span>  
  
     <span data-ttu-id="98012-116">たとえば、名前の行、小文字列は X です。そのため、KNA1 [名前] 列には、大文字と小文字の両方の文字を格納できます。</span><span class="sxs-lookup"><span data-stu-id="98012-116">For example, for the NAME row the LOWERCASE column is X. So, the NAME column in KNA1 can store both uppercase and lowercase characters.</span></span> <span data-ttu-id="98012-117">ただし、小文字 LAND1 行の列が空です。</span><span class="sxs-lookup"><span data-stu-id="98012-117">However, for the LAND1 row the LOWERCASE column is empty.</span></span> <span data-ttu-id="98012-118">そのため、KNA1 テーブル内の LAND1 列は文字の大文字のみ格納できます。</span><span class="sxs-lookup"><span data-stu-id="98012-118">So, the LAND1 column in KNA1 table can only store uppercase characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98012-119">参照</span><span class="sxs-lookup"><span data-stu-id="98012-119">See Also</span></span>  
 [<span data-ttu-id="98012-120">特定の SAP アダプターのシナリオを SAP GUI を使用したタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="98012-120">Performing Tasks Using the SAP GUI for Specific SAP Adapter Scenarios</span></span>](../../adapters-and-accelerators/adapter-sap/performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)