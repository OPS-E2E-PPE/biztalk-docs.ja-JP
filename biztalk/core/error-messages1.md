---
title: エラー Messages1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages
ms.assetid: db9c9634-3f4b-4b38-b3ba-388e587fccd8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98c6c3f8e6b4e648d8f40add23ec45bb3821579f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347394"
---
# <a name="error-messages"></a>エラー メッセージ
次の表では、JD Edwards EnterpriseOne システムのエラー メッセージについて説明し、それらの考えられる修正方法を提供します。  
  
|エラー ID|考えられる原因/エラーの説明|考えられる修正|  
|--------------|-----------------------------------------|-------------------------|  
|E-JDE0027|JD Edwards EnterpriseOne JAR ファイルがありません。 JD Edwards EnterpriseOne 接続オブジェクトを取得できません。|資格情報を確認します。 CLASSPATH 設定およびログオン資格情報を確認します。 環境変数を参照してください。|  
|JDE0043|構成ファイル、ユーザー、パスワードをアプリ サーバー、ポート、環境、パスが正しくありません。 ログインに失敗しました。|ログイン資格情報を確認します。 環境変数を参照してください。|  
|JDE0048|Jdearglist.txt ファイルが存在しないか、空では場合、Microsoft BizTalk Adapter for JD Edwards EnterpriseOne を開いたときにログに情報メッセージが表示されます。|右揃えで配置して、左に空白が埋め込まれて自動的には、パラメーターの一覧を入力する、jdearglist.txt ファイルを更新します。 詳細については、次を参照してください。[文字列値の処理](../core/handling-string-values2.md)します。 Jdearglist を変更するたびに、そのビジネス オブジェクトのスキーマを再生成する必要があります。|  
|E-JDE0027|JD Edwards EnterpriseOne 接続オブジェクトを取得できません。 CLASSPATH および資格情報を確認してください。|Jdeinterop.ini の場所を確認します。|  
  
## <a name="see-also"></a>参照  
 [JD Edwards EnterpriseOne のトラブルシューティング](../core/troubleshooting-jd-edwards-enterpriseone.md)   
 [テクニカル リファレンス](../core/technical-reference6.md)