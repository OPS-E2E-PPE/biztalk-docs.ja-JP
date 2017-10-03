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
# <a name="how-to-assign-an-application-to-an-adapter"></a>アダプターにアプリケーションを割り当てる方法
ローカル アプリケーションとリモート サーバー間でやり取りされる情報を処理するためには、アダプターに少なくとも 1 つのアプリケーションを割り当てる必要があります。  
  
### <a name="to-assign-an-application-to-an-adapter"></a>アダプターにアプリケーションを割り当てるには  
  
1.  `ISSOPSAdmin.AssignApplicationToAdapter` を使用して、アダプターにアプリケーションを追加します。  
  
2.  現在アダプターに割り当てられているアプリケーションのリストを取得するには、`ISSOAdmin.GetApplicationsForAdapter` を使用します。  
  
3.  以上の作業を終えた後、アダプターからアプリケーションを削除する場合は、`ISSOPSAdmin.RemoveApplicationFromAdapter` を使用します。