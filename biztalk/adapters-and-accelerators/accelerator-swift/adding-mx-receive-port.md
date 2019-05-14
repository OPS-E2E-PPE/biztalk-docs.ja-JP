---
title: 受信ポートの追加 MX |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4818d6af-df1d-481e-becf-1af633735248
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d95c9b97b18e20e2a852c5a1507d1110733e481b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378715"
---
# <a name="adding-mx-receive-port"></a>受信ポートの MX を追加します。
**追加するには、MX 受信ポートを使用します。**  
  
1.  開始**BizTalk Server 管理**コンソール。  
  
2.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**を展開し**BizTalk アプリケーション 1**します。  
  
3.  右クリック**受信ポート**、 をポイント**新規**、 をクリックし、**一方向の受信ポート**します。  
  
4.  受信ポートのプロパティ ダイアログ ボックスの 名前 ボックスに入力**MX_ の受信ポート**します。  
  
5.  をクリックして**適用**をクリックして、ポートのバインド**OK**します。  
  
6.  右クリック**受信場所**、 をポイント**新規**、 をクリックし、**一方向の受信場所**します。  
  
7.  受信ポートのダイアログ ボックスのをクリックして**MX_ の受信ポート**、順にクリックします**OK**します。  
  
8.  受信場所のプロパティ ダイアログ ボックスの 名前 ボックスに入力**MX_ 受信場所**します。  
  
9. テキスト ボックスに、トランスポート セクションで、ドロップダウン リストをクリックし、**ファイル**します。  
  
10. をクリックして、**構成**型のドロップダウン リストの右側にボタンをクリックします。  
  
11. [FILE トランスポートのプロパティ] ダイアログ ボックスで、**参照**、ファイルの場所を選択します。  
  
12. FILE トランスポートのプロパティ ダイアログ ボックスで、ことを確認します\*.xml が、ファイル マスク ボックスに入力し、クリックして**OK**します。  
  
13. 受信場所のプロパティ ダイアログ ボックスで、受信ハンドラー ボックスの biztalkserverapplication を入力することを確認します。  
  
14. パイプラインの受信ボックスに、次のように選択します**受信パイプライン**(パイプライン プロジェクトに配置されている受信パイプライン) ドロップダウン リストから、クリック**適用**、 をクリックし、 **ok。**.  
  
15. 構成したをクリックした場所を右クリックして**を有効にする**します。