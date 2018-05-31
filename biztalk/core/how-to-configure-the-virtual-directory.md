---
title: 仮想ディレクトリを構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: f00c5f75062ffd084cd19f23bfa66768d3d67ca5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969008"
---
# <a name="how-to-configure-the-virtual-directory"></a>仮想ディレクトリを構成する方法
このトピックでは、仮想ディレクトリを構成し、ユーザーのアプリケーションを検証する手順について説明します。  
  
### <a name="to-configure-the-virtual-directory"></a>仮想ディレクトリを構成するには  
  
1.  %systemdrive% で、仮想ディレクトリとして構成するフォルダーを作成します。  
  
2.  をクリックして**開始**、 をポイント**プログラム**、 をクリックして**管理ツール**、 をクリック**インターネット インフォメーション サービス (IIS) マネージャー**です。  
  
3.  展開**\<サーバー名\>** 順に展開**サイト**です。  
  
4.  右クリック**Default Web Site**  をクリック**仮想ディレクトリの追加**です。  
  
5.  **仮想ディレクトリの追加** ダイアログ ボックスで、別名を入力します。  
  
6.  手順 1. で作成したフォルダーのパスを入力します。 またはをクリックして **([...])** フォルダーの場所を参照します。  
  
7.  **[OK]** をクリックします。 下のフォルダーが表示されます、 **Default Web Site**フォルダーです。  
  
8.  フォルダーを右クリックし、をクリックして**アプリケーションへの変換**です。  
  
9. **アプリケーションの追加**ダイアログ ボックスで、をクリックして**OK**です。 フォルダーがアプリケーションに変換されます (アイコンがフォルダー アイコンから Web サイト アイコンに変化します)。  
  
## <a name="see-also"></a>参照  
 [アダプターのセキュリティ保護](../core/security-in-biztalk-adapter-for-peoplesoft-enterprise.md)