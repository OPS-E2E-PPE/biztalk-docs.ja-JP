---
title: 'シングル サインオン: イベント 10806 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be61b0a48dde7b1c8de9ec716f4f9426c39fa0cd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002699"
---
# <a name="single-sign-on-event-10806"></a>シングル サインオン: イベント 10806
## <a name="details"></a>詳細  
  
|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  製品名   |                             エンタープライズ シングル サインオン                             |
| 製品バージョン |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    イベント ID     |                                       10806                                       |
|  イベント ソース   |                                      ENTSSO                                       |
|    コンポーネント    |                                        なし                                        |
|  シンボル名  |                         ENTSSO_E_APP_ASSIGNED_TO_ADAPTER                          |
|  メッセージ テキスト   | アプリケーションは、現在アダプターに割り当てられているため削除できません。 |
  
## <a name="explanation"></a>説明  
 アプリケーションがアダプターに割り当てられている場合、アプリケーションを削除できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 アダプターからアプリケーションの割り当てを解除し、アプリケーションを削除します。