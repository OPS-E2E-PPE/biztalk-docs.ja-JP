---
title: 仮想ディレクトリを構成する方法 |Microsoft Docs
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
- applications, verifying for users
- verifying applications for users
ms.assetid: 3da16524-8238-426a-88f8-434be5992e13
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d4a0e35a4d88c9f8a64074cef40a9c701e5e7d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385975"
---
# <a name="how-to-configure-the-virtual-directory"></a>仮想ディレクトリを構成する方法
このトピックでは、仮想ディレクトリを構成してユーザーのアプリケーションを確認する手順について説明します。  
  
### <a name="to-configure-the-virtual-directory"></a>仮想ディレクトリを構成するには  
  
1.  %Systemdrive%、仮想ディレクトリとして構成するフォルダーを作成します。  
  
2.  クリックして**開始**、 をポイント**プログラム**、 をクリックして**管理ツール**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
3.  展開**\<サーバー名\>** 順に展開**サイト**します。  
  
4.  右クリック**既定の Web サイト**クリック**仮想ディレクトリの追加**します。  
  
5.  **仮想ディレクトリの追加** ダイアログ ボックスで、エイリアスを入力します。  
  
6.  手順 1 で作成したフォルダーのパスを入力します。 またはをクリックして **([...])** フォルダーの場所を参照します。  
  
7.  **[OK]** をクリックします。 下のフォルダーに表示される、**既定の Web サイト**フォルダー。  
  
8.  フォルダーを右クリックし、をクリックして**アプリケーションへの変換**します。  
  
9. **アプリケーションの追加**ダイアログ ボックスで、をクリックして**OK**。 フォルダーは、アプリケーション (Web サイト アイコンをフォルダー アイコンから – アイコンの変更を確認できます) に変換されます。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)