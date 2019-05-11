---
title: エラーの設定 ページ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f10b8b-9a32-40ca-9ce4-0b69e159c36c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1129d0eb8894c777a76e129a3777cd0757594f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250151"
---
# <a name="fault-settings-page"></a>エラー設定ページ
図 1 は、フォールトの設定 ページを示します。 このページでは、さまざまな管理設定を変更できますが表示されます。  
  
 ![設定 ページの障害](../esb-toolkit/media/ch8-faultsettingspage.gif "Ch8 FaultSettingsPage")  
  
 **図 1**  
  
 **ESB 管理ポータルのエラーの設定 ページ**  
  
 次の一覧では、ESB 管理ポータルのエラーの設定 ページの機能を使用する方法について説明します。  
  
-   監査オプションを変更するには、監査するイベントごとにチェック ボックスを選択します。 使用可能なイベントは、エラーを再送信するときに、変更された設定の保存、編集、およびエラーの後に障害を正常に再送信が。  
  
-   ポータルでは、Portal Alert サービスによって生成されたアラートのキューを保持します。 このサービスでの設定を変更することができます、**アラート キュー オプション**ページのセクション。 有効にして、サービスを無効にする、または Microsoft Active Directory ディレクトリ サービスとのやり取りを指定するか、およびキュー バッチ サイズとポーリング間隔を制御できます。  
  
-   アラートの電子メール サービスの設定を変更するには、コントロールを使用して、**アラートの電子メール オプション**ページのセクション。 有効にするか、サービスを無効にします。電子メール サーバーと「差出人」のアドレスを指定します。ポーリング間隔とバッチ サイズを変更します。サービスで使用される XSLT ファイルへのパスを指定します。  
  
> [!NOTE]
>  インストールして、ESB ポータルと、ポータルのアラート サービスを構成する場合は、このページで、値を入力する必要があります。 詳細については、次を参照してください。 [ESB 管理ポータルのインストール](http://go.microsoft.com/fwlink/?LinkId=188554)します。