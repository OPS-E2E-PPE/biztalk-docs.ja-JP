---
title: アプリケーションをアダプターに割り当てる方法 |Microsoft Docs
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2ca8850-6789-455b-be53-56f126605c06
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 8e473c10f8e0828389f83293bc7dd219786548c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342723"
---
# <a name="how-to-assign-an-application-to-an-adapter"></a><span data-ttu-id="87d45-102">アプリケーションをアダプターに割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="87d45-102">How to Assign an Application to an Adapter</span></span>
<span data-ttu-id="87d45-103">ローカル アプリケーションとリモート サーバー間でやり取りされる情報を処理するためには、アダプターに少なくとも 1 つのアプリケーションを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="87d45-103">To process information between a local application and a remote server, an adapter must have one or more applications assigned to it.</span></span>  
  
### <a name="to-assign-an-application-to-an-adapter"></a><span data-ttu-id="87d45-104">アダプターにアプリケーションを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="87d45-104">To assign an application to an adapter</span></span>  
  
1.  <span data-ttu-id="87d45-105">`ISSOPSAdmin.AssignApplicationToAdapter` を使用して、アダプターにアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="87d45-105">Add the application to the adapter by using `ISSOPSAdmin.AssignApplicationToAdapter`.</span></span>  
  
2.  <span data-ttu-id="87d45-106">現在アダプターに割り当てられているアプリケーションのリストを取得するには、`ISSOAdmin.GetApplicationsForAdapter` を使用します。</span><span class="sxs-lookup"><span data-stu-id="87d45-106">You can retrieve the current list of applications assigned to an adapter by using `ISSOAdmin.GetApplicationsForAdapter`.</span></span>  
  
3.  <span data-ttu-id="87d45-107">以上の作業を終えた後、アダプターからアプリケーションを削除する場合は、`ISSOPSAdmin.RemoveApplicationFromAdapter` を使用します。</span><span class="sxs-lookup"><span data-stu-id="87d45-107">Once you are finished, you can remove an application from an adapter by using `ISSOPSAdmin.RemoveApplicationFromAdapter`.</span></span>