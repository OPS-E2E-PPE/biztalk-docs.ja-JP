---
title: "仮想ディレクトリを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- virtual directory, configuring
- configuring virtual directory
- applications, verifying for users
- verifying applications for users
ms.assetid: 3da16524-8238-426a-88f8-434be5992e13
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b1461ac2ea0ef9cfee71965fc2cc800d617d1d4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-virtual-directory"></a>仮想ディレクトリを構成する方法
このトピックでは、仮想ディレクトリを構成し、ユーザーのアプリケーションを検証する手順について説明します。  
  
### <a name="to-configure-the-virtual-directory"></a>仮想ディレクトリを構成するには  
  
1.  %systemdrive% で、仮想ディレクトリとして構成するフォルダーを作成します。  
  
2.  をクリックして**開始**、 をポイント**プログラム**、 をクリックして**管理ツール**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。  
  
3.  展開**\<サーバー名 >**順に展開**サイト**です。  
  
4.  右クリック**Default Web Site**  をクリック**仮想ディレクトリの追加**です。  
  
5.  **仮想ディレクトリの追加** ダイアログ ボックスで、別名を入力します。  
  
6.  手順 1. で作成したフォルダーのパスを入力します。 またはをクリックして**([...])**フォルダーの場所を参照します。  
  
7.  **[OK]**をクリックします。 下のフォルダーが表示されます、 **Default Web Site**フォルダーです。  
  
8.  フォルダーを右クリックし、をクリックして**アプリケーションへの変換**です。  
  
9. **アプリケーションの追加**ダイアログ ボックスで、をクリックして**OK**です。 フォルダーがアプリケーションに変換されます (アイコンがフォルダー アイコンから Web サイト アイコンに変化します)。  
  
## <a name="see-also"></a>参照  
 [シングル サインオンを使用します。](../core/using-single-sign-on2.md)