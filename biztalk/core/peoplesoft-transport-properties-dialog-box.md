---
title: PeopleSoft トランスポートのプロパティ ダイアログ ボックス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- PeopleSoft
helpviewer_keywords:
- PeopleSoft Transport Properties dialog box
ms.assetid: 660f0a0b-e076-4f4e-8b2a-6d976acfc5ce
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50362e60b982a2d304efea8c26f58019148e5c16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="peoplesoft-transport-properties-dialog-box"></a>PeopleSoft トランスポートのプロパティ ダイアログ ボックス
[PeopleSoft トランスポートのプロパティ] ダイアログ ボックスでは、アダプターに必要なプロパティを設定します。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**アダプタに必要なプロパティ**||  
|アプリケーション サーバーのパス|PeopleSoft サーバーのパスを入力 (たとえば、 `//psserver.domain.com:9000`)。|  
|JAVA_HOME|JAVA_HOME の場所の名前を入力 (たとえば、 `<drive:>\jdk1.4.2_08`)。|  
|Password|このユーザーのパスワードを入力します。|  
|PeopleSoft 8.x JAR ファイル|PeopleSoft JAR ファイルの場所のパスを入力 (たとえば、 `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`)。|  
|ユーザー名|ユーザーの名前を入力し、をクリックして**OK**です。|  
|**追加のパラメーター**||  
|データベースの日付形式|入力日付を表示する形式 (たとえば、**YYYY MM DD**)。<br /><br /> 日付は、キーとして使用する場合には別の形式があります。|  
|**同時実行制御**||  
|最大同時呼び出し数|数値の値を入力、 **Max Concurrent Calls**です。 この数値は、同時呼び出しの最大数 (例: 200) を表します。<br /><br /> このフィールドの既定値は -1 です。保護は発生しません。|  
|**接続**||  
|セッションの最大数|セッションの最大数を表す数値を入力します。<br /><br /> 既定の接続数は 40 です。|  
|**エージェントを更新します。**||  
|エージェントの更新|選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要時に自動的に再起動を強制します。<br /><br /> たとえば、サーバーとの接続が失われた場合や、サーバーに追加したものがアダプター ウィザードに表示されない場合に、処理を自動的に再起動することができます。|  
|**シングル サインオン**||  
|[関連アプリケーション]|シングル サインオン (SSO) を使用している場合のみ、一覧から関連アプリケーションを選択します。|  
|SSO の使用|選択**はい**SSO; を使用している場合、パスワードは必要ありませんここでします。 **注:**既にパスワードを入力したシングル サインオンを使用する場合は、パスワード フィールドおよび選択を右クリックして**交わしたパスワード**です。|  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for PeopleSoft Enterprise の UI リファレンス](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)