---
title: "シングル サインオン: イベント 11029 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd7cb5b0-532c-4f50-849d-4d1644026463
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5f24cee6fcbe7db5ce0b4f31d458a5a29118c3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11029"></a>シングル サインオン: イベント 11029
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11029|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_INFO_CASE_SENSITIVE|  
|メッセージ テキスト|SSO データベースでは、大文字と小文字が区別されます。 SSO サーバーは大文字と小文字を区別するモードで実行します。 Details.%r のマニュアルを参照してください。|  
  
## <a name="explanation"></a>説明  
 既定では、SSO サーバーでは大文字と小文字が区別されません。 ただし、SQL Server SSO データベースが大文字と小文字を区別するように構成されているので、SSO サーバーも大文字と小文字を区別するモードで実行します。  
  
## <a name="user-action"></a>ユーザーの操作  
 アプリケーション名および外部アカウント名は大文字と小文字が区別されるようになっているので、これらを指定するときはそのことに注意してください。 詳細については、次を参照してください。 [SSO サーバー](../core/sso-server.md)です。