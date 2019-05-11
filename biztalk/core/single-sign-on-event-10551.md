---
title: シングル サインオン:イベント 10551 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33434989-08d8-4d13-a3cc-4c5543add69c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87e1965abac7bf861cfc90cfb2981b5ac30bd5b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250257"
---
# <a name="single-sign-on-event-10551"></a>シングル サインオン:イベント 10551
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                   エンタープライズ シングル サインオン                                                                                                   |
| 製品バージョン |                                                                                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                   |
|    イベント ID     |                                                                                                             10551                                                                                                             |
|  イベント ソース   |                                                                                                            ENTSSO                                                                                                             |
|    コンポーネント    |                                                                                                              なし                                                                                                              |
|  シンボル名  |                                                                                                     SSO_WARN_INVALID_USER                                                                                                     |
|  メッセージ テキスト   | 指定したユーザーがこの application.%r 無効なために、マッピングを作成できませんでした。<br /><br /> ドメイン名: %1 %r<br /><br /> ユーザー名: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> アプリケーション ユーザー: %4 |
  
## <a name="explanation"></a>説明  
 指定したユーザーが無効です。 これは、入力エラーである可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告情報にリストされているユーザー名を修正して、マッピングを作成し、あることを確認するもう一度です。