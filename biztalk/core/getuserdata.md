---
title: GetUserData |Microsoft ドキュメント
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
ms.openlocfilehash: 57bc0ffcefc00e9fae20c7b2c8449c21c549b377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246386"
---
# <a name="getuserdata"></a><span data-ttu-id="c30b0-102">GetUserData</span><span class="sxs-lookup"><span data-stu-id="c30b0-102">GetUserData</span></span>
<span data-ttu-id="c30b0-103">現在のユーザー データをスタックにプッシュします。</span><span class="sxs-lookup"><span data-stu-id="c30b0-103">Pushes the current user data onto the stack.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c30b0-104">構文</span><span class="sxs-lookup"><span data-stu-id="c30b0-104">Syntax</span></span>  
  
```  
  
<wf:Operation Name="GetUserData" />  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c30b0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="c30b0-105">Parameters</span></span>  
 <span data-ttu-id="c30b0-106">[なし] :</span><span class="sxs-lookup"><span data-stu-id="c30b0-106">None.</span></span>  
  
## <a name="pushed-value"></a><span data-ttu-id="c30b0-107">プッシュされた値</span><span class="sxs-lookup"><span data-stu-id="c30b0-107">Pushed Value</span></span>  
 <span data-ttu-id="c30b0-108">現在のユーザー データが含まれた文字列です。</span><span class="sxs-lookup"><span data-stu-id="c30b0-108">String containing the current user data.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c30b0-109">解説</span><span class="sxs-lookup"><span data-stu-id="c30b0-109">Remarks</span></span>  
 <span data-ttu-id="c30b0-110">この操作は、フィルタ内では無効です。</span><span class="sxs-lookup"><span data-stu-id="c30b0-110">This operation is not valid inside of a filter.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c30b0-111">例</span><span class="sxs-lookup"><span data-stu-id="c30b0-111">Example</span></span>  
 <span data-ttu-id="c30b0-112">次のサンプルには、`GetUserData` 操作を使用したデータ項目 "UserData" の更新された式が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c30b0-112">The following sample contains an update expression for the data item "UserData" using the `GetUserData` operation.</span></span>  
  
```  
<ic:Update DataItemName="UserData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetUserData" />  
  </ic:Expression>  
</ic:Update>  
```