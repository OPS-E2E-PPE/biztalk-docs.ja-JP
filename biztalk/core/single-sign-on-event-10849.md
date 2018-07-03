---
title: 'シングル サインオン: イベント 10849 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fdfb1cea-e445-4318-9891-b6b70a266ca9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cb1d63cf12c19a8e2213c7506f1752f86a02a85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991851"
---
# <a name="single-sign-on-event-10849"></a>シングル サインオン: イベント 10849
## <a name="details"></a>詳細  
  
|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  製品名   |                            エンタープライズ シングル サインオン                             |
| 製品バージョン |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    イベント ID     |                                      10849                                       |
|  イベント ソース   |                                      ENTSSO                                      |
|    コンポーネント    |                                       なし                                        |
|  シンボル名  |                     ENTSSO_E_DIRECT_SYNC_NOT_ALLOWED_CREATE                      |
|  メッセージ テキスト   | ‘直接パスワード同期’ フラグを指定してアプリケーションを作成することはできません。 |
  
## <a name="explanation"></a>説明  
 ‘直接パスワード同期’ フラグを指定してアプリケーションを作成することはできません。  
  
## <a name="user-action"></a>ユーザーの操作  
 直接パスワード同期フラグを設定しないでアプリケーションを作成します。 その後、フィールドを追加および作成し、アプリケーションを有効にして、直接パスワード同期フラグを指定します。