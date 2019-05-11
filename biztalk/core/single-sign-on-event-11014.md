---
title: シングル サインオン:イベント 11014 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 71e4c9bd-8bda-46ca-9e76-f7b4fa033167
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aebd0225967e3165f19449b73488d8f938b349ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267275"
---
# <a name="single-sign-on-event-11014"></a>シングル サインオン:イベント 11014
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                          |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                エンタープライズ シングル サインオン                                                                 |
| 製品バージョン |                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    イベント ID     |                                                                          11014                                                                           |
|  イベント ソース   |                                                                          ENTSSO                                                                          |
|    コンポーネント    |                                                                           なし                                                                            |
|  シンボル名  |                                                                  SSO_ERROR_ACCESS_CHECK                                                                  |
|  メッセージ テキスト   | アクセス チェック failed.%r<br /><br /> クライアント ユーザー: %1\\% 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 追加データ: % 4 %r<br /><br /> エラー コード: %5 |
  
## <a name="explanation"></a>説明  
 クライアントと表示されているアプリケーションのアクセス チェックが失敗しました。  
  
## <a name="user-action"></a>ユーザーの操作  
 追加の情報には、問題を修正することが有効にする必要があります。 このエラーを回避するために、将来、減らすことができますも監査レベル。