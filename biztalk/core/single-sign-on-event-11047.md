---
title: 'シングル サインオン: イベント 11047 |Microsoft Docs'
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
ms.openlocfilehash: 8f1ee4f5eaea1dac2cb2033d4585e2f89807588e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991867"
---
# <a name="single-sign-on-event-11047"></a>シングル サインオン: イベント 11047
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                         |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                エンタープライズ シングル サインオン                                                                |
| 製品バージョン |                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                |
|    イベント ID     |                                                                          11047                                                                          |
|  イベント ソース   |                                                                         ENTSSO                                                                          |
|    コンポーネント    |                                                                           なし                                                                           |
|  シンボル名  |                                                                 SSO_ERROR_SSOSQL_FAILED                                                                 |
|  メッセージ テキスト   | SSOSQL を作成できませんでした。 この問題を修正するには、SSO を再インストールするか、Visual Studio コマンド プロンプトで 'regasm SSOSQL.dll' を試してみてください。%r<br /><br /> エラー コード: %1 |
  
## <a name="explanation"></a>説明  
 これはインストール エラーにより発生した可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 この問題を修正するには、SSO を再インストールするか、Visual Studio コマンド プロンプトで 'regasm SSOSQL.dll' を試してみます。