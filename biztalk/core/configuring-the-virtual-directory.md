---
title: 仮想ディレクトリの構成 |Microsoft Docs
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
ms.openlocfilehash: 05f694744076f4242309ed58a70903fb7aaedbda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355145"
---
# <a name="configuring-the-virtual-directory"></a>仮想ディレクトリの構成
このトピックでは、仮想ディレクトリを構成してユーザーのアプリケーションの確認の手順を示します。  
  
## <a name="configuring-the-directory"></a>ディレクトリの構成  
  
#### <a name="to-configure-the-virtual-directory"></a>仮想ディレクトリを構成するには  
  
1.  %Systemdrive%、仮想ディレクトリとして構成するフォルダーを作成します。  
  
2.  クリックして**開始**、 をポイント**プログラム**、 をクリックして**管理ツール**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
3.  展開**\<サーバー名\>** 順に展開**サイト**します。  
  
4.  右クリック**既定の Web サイト**クリック**仮想ディレクトリの追加**します。  
  
5.  **仮想ディレクトリの追加** ダイアログ ボックスで、エイリアスを入力します。  
  
6.  手順 1 で作成したフォルダーのパスを入力します。 またはをクリックして **([...])** フォルダーの場所を参照します。  
  
7.  **[OK]** をクリックします。 下のフォルダーに表示される、**既定の Web サイト**フォルダー。  
  
8.  フォルダーを右クリックし、をクリックして**アプリケーションへの変換**します。  
  
9. **アプリケーションの追加**ダイアログ ボックスで、をクリックして**OK**。 フォルダーは、アプリケーション (Web サイト アイコンをフォルダー アイコンから – アイコンの変更を確認できます) に変換されます。  
  
## <a name="verifying-an-application-for-a-user"></a>ユーザーに対するアプリケーションの確認  
 インターネット インフォメーション サービス (IIS) アプリケーションは高度な分離; で実行します。そのため、アプリケーションは、次の手順を使用して、BizTalk Server 分離ホスト ユーザー グループ内のユーザーのコンテキストで実行できることを確認する必要があります。  
  
#### <a name="to-verify-an-application-for-a-user"></a>ユーザーのアプリケーションを確認するには  
  
1.  コントロール パネルで、開く**管理ツール**、 をクリックし、**コンポーネント サービス**します。  
  
2.  COM + アプリケーションに移動します**コンポーネント サービス**します。  
  
3.  COM + アプリケーションを右クリックし、をクリックして**プロパティ**します。  
  
4.  をクリックして**識別**この COM + アプリケーションを BizTalk Server グループのメンバーであるユーザーに実行する id を変更します。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md)