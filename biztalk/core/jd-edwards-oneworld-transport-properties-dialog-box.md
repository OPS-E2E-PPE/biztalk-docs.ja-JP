---
title: "JD Edwards OneWorld トランスポートのプロパティ ダイアログ ボックス |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: JDEOneWorld
helpviewer_keywords: Transport Properties dialog box [JD Edwards OneWorld adapters]
ms.assetid: 34d6b5d0-4bd9-4522-a540-8415d3143762
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 625479ef124aad6d7c0b10cde34b45a142ff9f90
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="jd-edwards-oneworld-transport-properties-dialog-box"></a>[JD Edwards OneWorld トランスポートのプロパティ] ダイアログ ボックス
[JD Edwards OneWorld トランスポートのプロパティ] ダイアログ ボックスでは、アダプターに必要なプロパティを設定します。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**アダプタに必要なプロパティ**||  
|Host|ホスト サーバー コンピューターの名前を入力 (たとえば、 `actsvr1`)。<br /><br /> - または--<br /><br /> コンピューターの IP アドレスを入力 (たとえば、 `123.456.0.789`)。|  
|JAVA_HOME|JDK インストールへの完全なパスを入力します。|  
|JDEdwards 環境|JD Edwards OneWorld の環境の名前を入力 (たとえば、 `DV7333`)。<br /><br /> DV7333 は開発環境の一般名、PY7333 はプロトタイプ環境の一般名、PD7333 は実稼働環境の一般名です。|  
|JDEdwards JAR ファイル|各 JAR ファイルの完全パスとファイル名を入力します。<br /><br /> -Connector.jar<br />-Kernel.jar<br />-JDEJAccess.jar<br />-BTSLIBInterop.jar<br /><br /> 各 jar ファイルは、セミコロン (;) とスペースなしで区切る必要があります (たとえば、 `<c:>\Connector.jar;<c:>\Kernel.jar;`)。|  
|Password|ユーザーのパスワードを入力します。 シングル サインオン (SSO) を使用しない場合は、BizTalk Adapter for JDEdwards OneWorld でサーバー システムにアクセスするための資格情報パラメーターを設定する必要があります。 パスワードは、ユーザー名に対応します。 パスワードでは、データベースにアクセスするときに付与される特権を決定します。|  
|ポート|入力した数値識別子、送信ポートまたは受信ポート (たとえば、 `6009`)。|  
|ユーザー名|ユーザーの名前を入力し、クリックして**OK**です。|  
|最大同時呼び出し数|数値の値を入力、 **Max Concurrent Calls**です。 この番号がなど、同時呼び出しの最大数を表す**10**です。<br /><br /> このフィールドの既定値は**5**、発生保護れないことを意味します。|  
|エージェントの更新|選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。<br /><br /> たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものが Microsoft アダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。|  
|[関連アプリケーション]|SSO を使用している場合にのみ、一覧から関連アプリケーションを選択します。|  
|SSO の使用|選択**はい**SSO; を使用している場合、パスワードは必要ありませんここでします。|  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)   
 [関連アプリケーションの作成](../core/creating-affiliate-applications3.md)   
 [BizTalk Adapter for JDE OneWorld の UI リファレンス](../core/ui-reference-for-biztalk-adapter-for-jde-oneworld.md)