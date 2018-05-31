---
title: エラーの設定 ページ |Microsoft ドキュメント
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
ms.openlocfilehash: a5ce03e5284122e8c1de9bd4e5c2d69c392174e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294146"
---
# <a name="fault-settings-page"></a>[エラーの設定] ページ
図 1 は、フォールトの設定 ページを示します。 このページには、変更可能な管理の設定の範囲が表示されます。  
  
 ![エラーの設定 ページ](../esb-toolkit/media/ch8-faultsettingspage.gif "Ch8 FaultSettingsPage")  
  
 **図 1**  
  
 **ESB 管理ポータル フォールトの設定 ページ**  
  
 次の一覧では、ESB 管理ポータル フォールトの設定 ページの機能を使用する方法について説明します。  
  
-   監査オプションを変更するには、監査する各イベントのチェック ボックスを選択します。 使用可能なイベントは、エラーを再送信するときに、変更した設定の保存、編集、およびエラーの後に障害を正常に再送信です。  
  
-   ポータルでは、Portal Alert サービスによって生成されたアラートのキューを保持します。 このサービスの設定を変更することができます、**キューのアラート オプション**ページのセクションです。 有効にして、サービスを無効にする、または Microsoft Active Directory ディレクトリ サービスとの相互作用を指定するか、しキュー バッチ サイズとポーリング間隔を制御できます。  
  
-   アラートの電子メール サービスの設定を変更するには、コントロールを使用して、**アラートの電子メール オプション**ページのセクションです。 有効にするにまたはサービスを無効にすることができます。電子メール サーバーと、"from"アドレス指定です。ポーリング間隔とバッチ サイズを変更します。サービスで使用される XSLT ファイルへのパスを指定します。  
  
> [!NOTE]
>  インストールして、ESB ポータルと Portal Alert サービスを構成する場合は、このページで、値を入力する必要があります。 詳細については、次を参照してください。 [ESB 管理ポータルをインストールする](http://go.microsoft.com/fwlink/?LinkId=188554)です。