---
title: 'シングル サインオン: イベント 10749 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10986736-77c0-42a7-b2bb-cd20f9f75fa6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 864c887cb6c115a2f766f9c06cbaa292fdbeace2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278458"
---
# <a name="single-sign-on-event-10749"></a>シングル サインオン: イベント 10749
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10749|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_WARN_PS_CLIENT_PING|  
|メッセージ テキスト|接続先 SSO サーバーに接続できませんでした。<br /><br /> サーバー上で SSO サービスが実行されており、サーバーに接続できることを確認してください。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> SSO サーバー名: %3 %r<br /><br /> エラー コード: %4|  
  
## <a name="explanation"></a>説明  
 この警告イベントは、SSO パスワード同期で、指定された接続先 SSO サーバーに接続できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 この警告を解消するには、次の操作を行います:   
  
-   ENTSSO サーバー スナップインを使用してサーバーを確認します。  
  
-   エンタープライズ シングル サインオン サービスが実行されていない場合は、起動します。  
  
-   接続先 SSO サーバーへのネットワーク接続を確認します。  
  
-   接続先 SSO サーバー上のファイアウォールを確認します。  
  
 詳細については、次のリソースを参照してください。  
  
-   [サーバー スナップインを使用する方法](../core/how-to-use-the-servers-snap-in.md)