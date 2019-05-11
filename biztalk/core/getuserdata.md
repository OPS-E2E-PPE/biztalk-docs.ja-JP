---
title: GetUserData |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c243555b-109f-47e3-8084-ab13a8e22ac5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8348e510d168725bf61ab05075162f15768915d6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344899"
---
# <a name="getuserdata"></a><span data-ttu-id="e2c71-102">GetUserData</span><span class="sxs-lookup"><span data-stu-id="e2c71-102">GetUserData</span></span>
<span data-ttu-id="e2c71-103">現在のユーザー データをスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="e2c71-103">Pushes the current user data onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2c71-104">構文</span><span class="sxs-lookup"><span data-stu-id="e2c71-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserData" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2c71-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="e2c71-105">Parameters</span></span>  
 <span data-ttu-id="e2c71-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="e2c71-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="e2c71-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="e2c71-107">Pushed Value</span></span>  
 <span data-ttu-id="e2c71-108">現在のユーザー データが含まれた文字列です。</span><span class="sxs-lookup"><span data-stu-id="e2c71-108">String containing the current user data.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2c71-109">コメント</span><span class="sxs-lookup"><span data-stu-id="e2c71-109">Remarks</span></span>  
 <span data-ttu-id="e2c71-110">この操作は、フィルタ内では無効です。</span><span class="sxs-lookup"><span data-stu-id="e2c71-110">This operation is not valid inside of a filter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2c71-111">例</span><span class="sxs-lookup"><span data-stu-id="e2c71-111">Example</span></span>  
 <span data-ttu-id="e2c71-112">次のサンプルには、`GetUserData` 操作を使用したデータ項目 "UserData" の更新された式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e2c71-112">The following sample contains an update expression for the data item "UserData" using the `GetUserData` operation.</span></span>  
  
```  
<ic:Update DataItemName="UserData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetUserData" />  
  </ic:Expression>  
</ic:Update>  
```