---
title: エラー Messages1 |Microsoft ドキュメント
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
ms.openlocfilehash: 80a44049c43c499ac05a8a6f296d11add934267a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-messages"></a>エラー メッセージ
次の表に、JD Edwards EnterpriseOne システムのエラー メッセージおよび可能な対応策を示します。  
  
|エラー ID|考えられる原因/エラーの説明|考えられる修正|  
|--------------|-----------------------------------------|-------------------------|  
|E-JDE0027|JD Edwards EnterpriseOne JAR ファイルが見つかりません。 JD Edwards EnterpriseOne 接続オブジェクトを取得できません。|資格情報を確認してください。 CLASSPATH 設定およびログオン資格情報を確認します。 環境変数を参照してください。|  
|I-JDE0043|アプリケーション サーバー、ポート、環境、構成ファイルのパス、ユーザー、パスワードが間違っています。 ログインに失敗しました。|ログイン資格情報を確認します。 環境変数を参照してください。|  
|I-JDE0048|Microsoft BizTalk Adapter for JD Edwards EnterpriseOne が開いているときに、jdearglist.txt ファイルが存在しないか、または空の場合、ログに情報メッセージが表示されます。|パラメーターの一覧を入力するには、自動的に右揃えになり左側に空白が埋め込まれるように、jdearglist.txt ファイルを更新してください。 詳細については、次を参照してください。[文字列値の処理](../core/handling-string-values2.md)です。 jdearglist を変更するごとに、そのビジネス オブジェクトのスキーマを再生成する必要があります。|  
|E-JDE0027|JD Edwards EnterpriseOne 接続オブジェクトを取得できません。 CLASSPATH および資格情報を確認してください。|jdeinterop.ini の場所を確認します。|  
  
## <a name="see-also"></a>参照  
 [JD Edwards EnterpriseOne のトラブルシューティング](../core/troubleshooting-jd-edwards-enterpriseone.md)   
 [テクニカル リファレンス](../core/technical-reference6.md)