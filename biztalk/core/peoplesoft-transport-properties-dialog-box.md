---
title: PeopleSoft トランスポートのプロパティ ダイアログ ボックス |Microsoft Docs
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
ms.openlocfilehash: 8134f51cd6ac0ef90b2ef204b4e6c6ee38f7b6b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65322169"
---
# <a name="peoplesoft-transport-properties-dialog-box"></a>PeopleSoft トランスポートのプロパティ ダイアログ ボックス
PeopleSoft トランスポートのプロパティ ダイアログ ボックスを使用して、アダプターに必要なプロパティを設定します。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**アダプタに必要なプロパティ**||  
|アプリケーション サーバーのパス|PeopleSoft server のパスを入力 (たとえば、 `//psserver.domain.com:9000`)。|  
|JAVA_HOME|JAVA_HOME の場所の名前を入力 (たとえば、 `<drive:>\jdk1.4.2_08`)。|  
|パスワード|このユーザーのパスワードを入力します。|  
|PeopleSoft 8.x JAR ファイル|PeopleSoft JAR ファイルの場所のパスを入力 (たとえば、 `<drive:>\JAR_FILES\Peoplesoft_8.4\psjoa.jar`)。|  
|[ユーザー名]|ユーザーの名前を入力し、をクリックして**OK**します。|  
|**追加のパラメーター**||  
|データベースの日付形式|入力日付を表示する形式 (たとえば、**- YYYY-MM-DD**)。<br /><br /> 日付には、キーとして使用する場合に、さまざまな形式があります。|  
|**同時実行制御**||  
|最大同時呼び出し数|数値を入力、**最大同時呼び出し数**します。 この数は、たとえば、200 の同時呼び出しの最大数を表します。<br /><br /> 既定値のこのフィールドが-1 の場合に発生します保護れないことを意味します。|  
|**Connection**||  
|セッションの最大数|セッションの最大数を表す数値を入力します。<br /><br /> 既定の接続数には 40 です。|  
|**エージェントを更新します。**||  
|エージェントの更新|選択**はい**の**エージェントの更新**runtimeagent.exe および browsingagent.exe の処理を必要な場合に自動的に再起動を強制します。<br /><br /> など、処理をサーバーとの接続が失われた場合、またはサーバーに追加して、アダプター ウィザードで選択範囲のない場合、自動的に再起動が必要です。|  
|**シングル サインオン**||  
|[関連アプリケーション]|シングル サインオン (SSO) を使用している場合にのみ、一覧から関連アプリケーションを選択します。|  
|SSO の使用|選択**はい**SSO; を使用している場合、パスワードは必要ありませんここでします。 **注:** 既にパスワードを入力したシングル サインオンを使用する場合は、パスワード フィールドと選択を右クリックして**パスワードの無効化**します。|  
  
## <a name="see-also"></a>参照  
 [BizTalk Adapter for PeopleSoft Enterprise の UI リファレンス](../core/ui-reference-for-biztalk-adapter-for-peoplesoft-enterprise.md)