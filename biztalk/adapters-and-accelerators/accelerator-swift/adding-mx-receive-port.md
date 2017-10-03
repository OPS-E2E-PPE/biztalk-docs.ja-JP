---
title: "受信ポートの追加 MX |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4818d6af-df1d-481e-becf-1af633735248
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69123b876bdda4b5f999277a1710cdeb1cb61fe7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-mx-receive-port"></a>MX を追加する受信ポート
**追加するには、MX 受信ポート。**  
  
1.  開始**BizTalk Server 管理コンソール**コンソールです。  
  
2.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**の順に展開および**BizTalk アプリケーション 1**です。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、クリックして**一方向の受信ポート**です。  
  
4.  受信ポートのプロパティ ダイアログ ボックスの 名前 ボックスに入力**MX_ の受信ポート**です。  
  
5.  をクリックして**適用**をクリックして、ポートのバインド**OK**です。  
  
6.  右クリック**受信場所**、 をポイント**新規**、クリックして**一方向の受信場所**です。  
  
7.  [受信ポート] ダイアログ ボックスのをクリックして**MX_ の受信ポート**、順にクリック**OK**です。  
  
8.  受信場所のプロパティ ダイアログ ボックスの 名前 ボックスに入力**MX_ 受信場所**です。  
  
9. セクションでは、トランスポート、テキスト ボックスのドロップダウン リストをクリックし、選択**ファイル**です。  
  
10. クリックして、**構成**型のドロップダウン リストの右側にあるボタンです。  
  
11. [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**、ファイルの場所を選択します。  
  
12. ファイル トランスポートのプロパティ ダイアログ ボックスでいることを確認\*.xml は、ファイル マスク ボックスに入力し、をクリックして**OK**です。  
  
13. 受信場所のプロパティ ダイアログ ボックスで、BizTalkServerApplication を受信するハンドラー ボックスに入力することを確認します。  
  
14. 受信パイプライン ボックスで選択**受信パイプライン**(パイプライン プロジェクトに配置されている受信パイプライン) ドロップダウン リストからをクリックして**適用**、クリックして**ok**.  
  
15. をクリックして、構成した場所を右クリックして**を有効にする**です。