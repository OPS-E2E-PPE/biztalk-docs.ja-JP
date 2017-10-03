---
title: "JD Edwards EnterpriseOne トランスポートのプロパティ ダイアログ ボックス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: JDE
helpviewer_keywords: Transport Properties dialog box [JD Edwards EnterpriseOne adapters
ms.assetid: 6a37eeb2-af91-4f58-9699-7a7cbe296862
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21bbb6b4469399aa1952d0a9bdcc41ff7e14c842
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="jd-edwards-enterpriseone-transport-properties-dialog-box"></a>[JD Edwards EnterpriseOne トランスポートのプロパティ] ダイアログ ボックス
[JD Edwards EnterpriseOne トランスポートのプロパティ] ダイアログ ボックスでは、アダプターに必要なプロパティを設定します。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**アダプタに必要なプロパティ**||  
|Host|ホスト サーバー コンピューターの名前を入力 (たとえば、 `actsvr1`)。<br /><br /> -または-<br /><br /> コンピューターの IP アドレスを入力 (たとえば、 `123.456.0.789`)。|  
|JAVA_HOME|JDK インストールへの完全なパスを入力します (たとえば、<br /><br /> `C:\jdk1sdk1.4.2_07`)。|  
|JDEdwards 環境|JD Edwards EnterpriseOne の環境の名前を入力 (たとえば、 `DV7333`)。<br /><br /> DV7333 は開発環境用の共通名です。PY7333 はプロトタイプ環境の、PD7333 は運用環境のそれぞれ共通名です。|  
|JDEdwards JAR ファイル|各 JAR ファイルの完全パスとファイル名を入力します。<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br /><br /> 各 jar ファイルはセミコロン (;) で区切る必要があり、セミコロンの前後にはスペースを入れません (例: <br /><br /> `<c:>\Connector.jar;<c:>\Kernel.jar;`)。|  
|Password|ユーザーのパスワードを入力します。 UseSingle サインオン (SSO) ではない場合は、BizTalk Adapter for JD Edwards EnterpriseOne サーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。 パスワードは、ユーザー名に対応します。 このパスワードは、データベースにアクセスする際に付与される特権を決定します。|  
|ポート|入力した数値識別子、送信ポートまたは受信ポート (たとえば、 `6009`)。|  
|[ユーザー名]|ユーザーの名前を入力し、をクリックして**OK**です。|  
|**Bootstrap Data Source に必要なプロパティ**||  
|Data Source Name|データ ソースの名前を入力します。 この名前はすべてのデータの種類に必須です。|  
|データベースの所有者|データベース所有者の名前を入力します。|  
|データベース サーバー名|データベース サーバーの名前を入力します。|  
|データベース サーバー ポート|データベース サーバー ポートの識別用の番号を入力します。|  
|データベースの種類|データベースの種類を示す単一の文字を入力します。 例:<br /><br /> **I** -iSeries<br /><br /> **O** -Oracle<br /><br /> **S** -SQL Server<br /><br /> **L** -SQL Server OLEDB<br /><br /> **W** -UDB|  
|物理データベース名|物理データベースの名前を入力します。 この名前はすべてのデータベースの種類に必須です。|  
|**同時実行制御**||  
|最大同時呼び出し数|数値の値を入力、 **Max Concurrent Calls**です。 この番号がなど、同時呼び出しの最大数を表す**10**です。<br /><br /> このフィールドの既定値は 5 です。|  
|**エージェントを更新します。**||  
|エージェントの更新|選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。<br /><br /> たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。|  
|**セキュリティ サーバー**||  
|セキュリティ サーバー名|セキュリティ サーバーの名前を入力します。 このフィールドは省略可能で、既定値は JD Edwards サーバー ホストです。|  
|サービス名接続|セキュリティ サーバーとオブジェクト構成マッピング (OCM) で使用されるポート番号を入力します。 既定値は JD Edwards サーバー ポートです。|  
|**シングル サインオン**||  
|[関連アプリケーション]|エンタープライズ シングル サインオン (SSO) を使用する場合にのみ、ドロップダウン リストから関連アプリケーションを選択します。|  
|SSO の使用|選択**はい**SSO; を使用している場合、パスワードは必要ありませんここでします。|  
  
## <a name="see-also"></a>参照  
 [シングル サインオンを使用します。](../core/using-single-sign-on1.md)   
 [関連アプリケーションの作成](../core/creating-affiliate-applications4.md)   
 [BizTalk Adapter for JD Edwards EnterpriseOne の UI リファレンス](../core/ui-reference-for-biztalk-adapter-for-jd-edwards-enterpriseone.md)