---
title: シングル サインオン:イベント 11047 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aa4eb1ae-45a6-4e0c-9af6-6bf1ed63acfb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97d70d94ffad94b4a81d09c821469c4adbfbe775
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400957"
---
# <a name="single-sign-on-event-11047"></a>シングル サインオン:イベント 11047
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                エンタープライズ シングル サインオン                                                                |
| 製品バージョン |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    イベント ID     |                                                                          11047                                                                          |
|  イベント ソース   |                                                                         ENTSSO                                                                          |
|    コンポーネント    |                                                                           なし                                                                           |
|  シンボル名  |                                                                 SSO_ERROR_SSOSQL_FAILED                                                                 |
|  メッセージ テキスト   | SSOSQL を作成できませんでした。 問題を解決するには、SSO を再インストールするか、Visual Studio コマンド prompt.%r から 'regasm Ssosql.dll' を試してみる<br /><br /> エラー コード: %1 |
  
## <a name="explanation"></a>説明  
 可能性があります、これは、インストール エラーが発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 問題を解決するには、SSO を再インストールするか、Visual Studio コマンド プロンプトで 'regasm Ssosql.dll' をお試しいただけます。