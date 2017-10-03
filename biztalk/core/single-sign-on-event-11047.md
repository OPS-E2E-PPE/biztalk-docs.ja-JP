---
title: "シングル サインオン: イベント 11047 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa4eb1ae-45a6-4e0c-9af6-6bf1ed63acfb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e16c2fa899642f20c67e171d0bd8f9536b6add2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11047"></a>シングル サインオン: イベント 11047
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11047|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_ERROR_SSOSQL_FAILED|  
|メッセージ テキスト|SSOSQL を作成できませんでした。 この問題を修正するには、SSO を再インストールするか、Visual Studio コマンド プロンプトで 'regasm SSOSQL.dll' を試してみてください。%r<br /><br /> エラー コード: %1|  
  
## <a name="explanation"></a>説明  
 これはインストール エラーにより発生した可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 この問題を修正するには、SSO を再インストールするか、Visual Studio コマンド プロンプトで 'regasm SSOSQL.dll' を試してみます。