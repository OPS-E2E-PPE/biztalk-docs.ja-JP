---
title: 仮想ディレクトリの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
ms.assetid: 548e3bee-66bc-424c-895d-e8672a3d6301
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcd87b89c6c23e709f21e78e3ea98dd2b84575ca
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968816"
---
# <a name="configuring-the-virtual-directory"></a>仮想ディレクトリの構成
このトピックでは、仮想ディレクトリを構成してユーザーのアプリケーションを確認する手順を示します。  
  
## <a name="configuring-the-directory"></a>ディレクトリの構成  
  
#### <a name="to-configure-the-virtual-directory"></a>仮想ディレクトリを構成するには  
  
1.  %systemdrive% で、仮想ディレクトリとして構成するフォルダーを作成します。  
  
2.  をクリックして**開始**、 をポイント**プログラム**、 をクリックして**管理ツール**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。  
  
3.  展開**\<サーバー名\>** 順に展開**サイト**です。  
  
4.  右クリック**Default Web Site**  をクリック**仮想ディレクトリの追加**です。  
  
5.  **仮想ディレクトリの追加** ダイアログ ボックスで、別名を入力します。  
  
6.  手順 1. で作成したフォルダーのパスを入力します。 またはをクリックして **([...])** フォルダーの場所を参照します。  
  
7.  **[OK]** をクリックします。 下のフォルダーが表示されます、 **Default Web Site**フォルダーです。  
  
8.  フォルダーを右クリックし、をクリックして**アプリケーションへの変換**です。  
  
9. **アプリケーションの追加**ダイアログ ボックスで、をクリックして**OK**です。 フォルダーがアプリケーションに変換されます (アイコンがフォルダー アイコンから Web サイト アイコンに変化します)。  
  
## <a name="verifying-an-application-for-a-user"></a>ユーザーに対するアプリケーションの確認  
 インターネット インフォメーション サービス (IIS) アプリケーションは高分離レベルで実行されます。したがって、次の手順を使用して、このアプリケーションが BizTalk Server 分離ホスト ユーザー グループのユーザーのコンテキストで実行できることを確認する必要があります。  
  
#### <a name="to-verify-an-application-for-a-user"></a>ユーザーのアプリケーションを検証するには  
  
1.  コントロール パネルで、開く**管理ツール**、クリックして**コンポーネント サービス**です。  
  
2.  COM + アプリケーションに移動**コンポーネント サービス**です。  
  
3.  COM + アプリケーションを右クリックし、をクリックして**プロパティ**です。  
  
4.  をクリックして**識別**BizTalk Server グループのメンバーであるユーザーにこの COM + アプリケーションを実行する id を変更するとします。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)