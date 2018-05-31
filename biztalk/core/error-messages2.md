---
title: エラー Messages2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- error messages, JD Edwards OneWorld adapters
- adapters [JD Edwards OneWorld adapters], error messages
- JD Edwards OneWorld adapters, error messages
ms.assetid: 9fb65d50-83c6-426e-a0d6-674800ecf70f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84b26891592162c553fb270d2d8c9482f1c2b4d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241898"
---
# <a name="error-messages"></a>エラー メッセージ
次の表は、JD Edwards OneWorld システムのエラー メッセージと、その修正方法の説明です。  
  
|エラー ID|考えられる原因/エラーの説明|考えられる修正|  
|--------------|-----------------------------------------|-------------------------|  
|**E JDE0002**|JD Edwards OneWorld JAR ファイルが見つかりません。<br /><br /> JD Edwards OneWorld Java Data Bean のクラス オブジェクトをインスタンス化できませんでした。|リポジトリのパスを確認します。<br /><br /> 詳細については、次を参照してください。[基本型](../core/basic-types1.md)です。|  
|**E JDE0027**|JD Edwards OneWorld JAR ファイルが見つかりません。 JD Edwards OneWorld 接続オブジェクトを取得できません。|CLASSPATH 環境変数を確認します。<br /><br /> 「CLASSPATH の更新」を参照してください。<br /><br /> 資格情報を確認してください。<br /><br /> 詳細については、次を参照してください。[基本型](../core/basic-types1.md)です。|  
||JD Edwards OneWorld JAR ファイルが見つかりません。<br /><br /> リポジトリのパスに誤りがあります。|Jdeinterop.ini の場所を確認します。 Jdeinterop.ini ファイルに設定されたリポジトリのパスを確認します。<br /><br /> JD Edwards OneWorld ビジネス プロセスを別のコンピューターにインポートする場合は、手動で jdeinterop.ini をコピーする必要があります。|  
||JD Edwards OneWorld 接続オブジェクトを取得できません。|CLASSPATH 設定とログオン資格情報を確認します。|  
|**I JDE0043**|アプリケーション サーバー、ポート、環境、構成ファイルのパス、ユーザー、パスワードが間違っています。<br /><br /> ログオンに失敗しました。|ログオン資格情報を確認します。<br /><br /> 詳細については、次を参照してください。[基本型](../core/basic-types1.md)です。|  
|**I JDE0048**|jdearglist.txt ファイルが存在しないか空の場合、Microsoft BizTalk Adapter for JD Edwards OneWorld が開くときに情報メッセージがログに記録されます。|パラメーターの一覧を入力するには、自動的に右揃えになり左側に空白が埋め込まれるように、jdearglist.txt ファイルを更新してください。<br /><br /> 参照してください[文字列値の処理](../core/handling-string-values1.md)です。<br /><br /> jdearglist を変更するごとに、そのビジネス オブジェクトのスキーマを再生成する必要があります。|  
  
## <a name="see-also"></a>参照  
 [付録 a: データ型](../core/appendix-a-data-types.md)   
 [JD Edwards OneWorld のトラブルシューティング](../core/troubleshooting-jd-edwards-oneworld.md)