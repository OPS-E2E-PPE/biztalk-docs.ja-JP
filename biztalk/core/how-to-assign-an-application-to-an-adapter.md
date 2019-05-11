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
# <a name="how-to-assign-an-application-to-an-adapter"></a>アプリケーションをアダプターに割り当てる方法
ローカル アプリケーションとリモート サーバー間でやり取りされる情報を処理するためには、アダプターに少なくとも 1 つのアプリケーションを割り当てる必要があります。  
  
### <a name="to-assign-an-application-to-an-adapter"></a>アダプターにアプリケーションを割り当てるには  
  
1.  `ISSOPSAdmin.AssignApplicationToAdapter` を使用して、アダプターにアプリケーションを追加します。  
  
2.  現在アダプターに割り当てられているアプリケーションのリストを取得するには、`ISSOAdmin.GetApplicationsForAdapter` を使用します。  
  
3.  以上の作業を終えた後、アダプターからアプリケーションを削除する場合は、`ISSOPSAdmin.RemoveApplicationFromAdapter` を使用します。