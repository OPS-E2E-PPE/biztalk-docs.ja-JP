---
title: エラー Messages2 |Microsoft Docs
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
ms.openlocfilehash: 6de1d180bb0f44eac2af17eee03577ee4b45d70b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388609"
---
# <a name="error-messages"></a>エラー メッセージ
次の表は、JD Edwards OneWorld システムのエラー メッセージについて説明し、それらの考えられる修正方法を提供します。  
  
|エラー ID|考えられる原因/エラーの説明|考えられる修正|  
|--------------|-----------------------------------------|-------------------------|  
|**E-JDE0002**|JD Edwards OneWorld JAR ファイルがありません。<br /><br /> JD Edwards OneWorld Java Data Bean のクラスのオブジェクトをインスタンス化できませんでした。|リポジトリのパスを確認します。<br /><br /> 詳細については、次を参照してください。[基本型](../core/basic-types1.md)します。|  
|**E JDE0027**|JD Edwards OneWorld JAR ファイルがありません。 JD Edwards OneWorld 接続オブジェクトを取得できません。|CLASSPATH 環境変数を確認します。<br /><br /> CLASSPATH の更新を参照してください。<br /><br /> 資格情報を確認します。<br /><br /> 詳細については、次を参照してください。[基本型](../core/basic-types1.md)します。|  
||JD Edwards OneWorld JAR ファイルがありません。<br /><br /> リポジトリの正しくないパス。|Jdeinterop.ini の場所を確認します。 Jdeinterop.ini ファイルに設定されたリポジトリのパスを確認します。<br /><br /> JD Edwards OneWorld のビジネス プロセスを別のコンピューターにインポートするときに、手動で jdeinterop.ini をコピーする必要があります。|  
||JD Edwards OneWorld 接続オブジェクトを取得できません。|CLASSPATH 設定とログオン資格情報を確認します.|  
|**JDE0043**|構成ファイル、ユーザー、パスワードをアプリ サーバー、ポート、環境、パスが正しくありません。<br /><br /> ログオンに失敗しました。|ログオン資格情報を確認します。<br /><br /> 詳細については、次を参照してください。[基本型](../core/basic-types1.md)します。|  
|**JDE0048**|Jdearglist.txt ファイルが存在しないか、空では場合、Microsoft BizTalk Adapter for JD Edwards OneWorld を開いたときにログに情報メッセージが表示されます。|右揃えで配置して、左に空白が埋め込まれて自動的には、パラメーターの一覧を入力する、jdearglist.txt ファイルを更新します。<br /><br /> 参照してください[文字列値を処理する](../core/handling-string-values1.md)します。<br /><br /> Jdearglist を変更するたびに、そのビジネス オブジェクトのスキーマを再生成する必要があります。|  
  
## <a name="see-also"></a>参照  
 [付録 a:データ型](../core/appendix-a-data-types.md)   
 [JD Edwards OneWorld のトラブルシューティング](../core/troubleshooting-jd-edwards-oneworld.md)