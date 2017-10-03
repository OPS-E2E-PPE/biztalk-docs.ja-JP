---
title: "アダプターにアプリケーションを割り当てる方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1ea2773-c53c-40a0-a312-015191746451
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5052d06576988ed71da8458a9d55115fb0b1c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-an-application-to-an-adapter"></a><span data-ttu-id="b2e40-102">アダプターにアプリケーションを割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="b2e40-102">How to Assign an Application to an Adapter</span></span>
<span data-ttu-id="b2e40-103">ローカル アプリケーションとリモート サーバー間でやり取りされる情報を処理するためには、アダプターに少なくとも 1 つのアプリケーションを割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2e40-103">To process information between a local application and a remote server, an adapter must have one or more applications assigned to it.</span></span>  
  
### <a name="to-assign-an-application-to-an-adapter"></a><span data-ttu-id="b2e40-104">アダプターにアプリケーションを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="b2e40-104">To assign an application to an adapter</span></span>  
  
1.  <span data-ttu-id="b2e40-105">`ISSOPSAdmin.AssignApplicationToAdapter` を使用して、アダプターにアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="b2e40-105">Add the application to the adapter by using `ISSOPSAdmin.AssignApplicationToAdapter`.</span></span>  
  
2.  <span data-ttu-id="b2e40-106">現在アダプターに割り当てられているアプリケーションのリストを取得するには、`ISSOAdmin.GetApplicationsForAdapter` を使用します。</span><span class="sxs-lookup"><span data-stu-id="b2e40-106">You can retrieve the current list of applications assigned to an adapter by using `ISSOAdmin.GetApplicationsForAdapter`.</span></span>  
  
3.  <span data-ttu-id="b2e40-107">以上の作業を終えた後、アダプターからアプリケーションを削除する場合は、`ISSOPSAdmin.RemoveApplicationFromAdapter` を使用します。</span><span class="sxs-lookup"><span data-stu-id="b2e40-107">Once you are finished, you can remove an application from an adapter by using `ISSOPSAdmin.RemoveApplicationFromAdapter`.</span></span>