---
title: 'シングル サインオン: イベント 11062 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 55c7c2ea-c671-4853-ac64-8cb80bba98b0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50df4834f92eff7cc679c051f529f4dbaefc4335
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970143"
---
# <a name="single-sign-on-event-11062"></a>シングル サインオン: イベント 11062
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                        |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                       エンタープライズ シングル サインオン                                                                                        |
| 製品バージョン |                                                                       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                       |
|    イベント ID     |                                                                                                 11062                                                                                                  |
|  イベント ソース   |                                                                                                 ENTSSO                                                                                                 |
|    コンポーネント    |                                                                                                  なし                                                                                                   |
|  シンボル名  |                                                                                    SSO_WARN_PASSWORD_FILTER_FAILED                                                                                     |
|  メッセージ テキスト   | パスワードのフィルター処理が失敗しました。 パスワード フィルターは使用されません。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> パスワード フィルタ文字列: % 2 %r<br /><br /> 追加データ: % 3 %r<br /><br /> エラー コード: %4 |
  
## <a name="explanation"></a>説明  
 パスワード フィルターの作成中にエラーが発生し、フィルターは作成されませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 パスワード フィルターの作成ウィザードを使用して、パスワード フィルターを作成するを参照してください。[パスワード フィルターを使用する方法](../core/how-to-use-password-filters.md)します。