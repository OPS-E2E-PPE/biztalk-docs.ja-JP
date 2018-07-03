---
title: 'シングル サインオン: イベント 10566 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd140b-5503-40f8-bf5d-604fa763989e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4748670e128b5b3a9717e2e430acb976da7bb4d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015091"
---
# <a name="single-sign-on-event-10566"></a>シングル サインオン: イベント 10566
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                     エンタープライズ シングル サインオン                                                                      |
| 製品バージョン |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    イベント ID     |                                                                               10566                                                                                |
|  イベント ソース   |                                                                               ENTSSO                                                                               |
|    コンポーネント    |                                                                                なし                                                                                 |
|  シンボル名  |                                                                  SSO_WARN_CANNOT_UPDATE_APP_FLAGS                                                                  |
|  メッセージ テキスト   | このアプリケーションの指定されたフラグの一部を更新できません。 これらは無視されます。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> 指定フラグ マスク: %2 |
  
## <a name="explanation"></a>説明  
 アプリケーションの特定のフラグを変更できません。 たとえば、アプリケーションの種類を単独からグループに変更することができません。このようなアプリケーションのフラグは、警告のテキストに示されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 ユーザーによる操作は不要です。