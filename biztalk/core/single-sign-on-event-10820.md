---
title: 'シングル サインオン: イベント 10820 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2da93a2c-d00d-4ca0-a0cf-453cee4bf3c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78b566c4dfe4437017b743228c9bae2631c79a00
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011659"
---
# <a name="single-sign-on-event-10820"></a>シングル サインオン: イベント 10820
## <a name="details"></a>詳細  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  製品名   |                                  エンタープライズ シングル サインオン                                   |
| 製品バージョン |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    イベント ID     |                                            10820                                             |
|  イベント ソース   |                                            ENTSSO                                            |
|    コンポーネント    |                                             なし                                              |
|  シンボル名  |                                ENTSSO_E_REQUIRE_OLD_PASSWORD                                 |
|  メッセージ テキスト   | 外部アカウントのパスワードを変更するときに、アダプターで古いパスワードを指定する必要があります。 |
  
## <a name="explanation"></a>説明  
 このアプリケーションは、パスワード同期アダプターに古いパスワードの指定を求めるように構成されています。  
  
## <a name="user-action"></a>ユーザーの操作  
 パスワード同期アダプターの構成を確認します。