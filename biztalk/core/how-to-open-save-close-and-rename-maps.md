---
title: "開く、保存、終了、およびマップの名前を変更する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9aa88ca7-a731-4295-8692-6dd36fdf0872
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9383dd3751f9ccdd7790b0215e596eba95dc4a45
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-open-save-close-and-rename-maps"></a>マップを開く、保存、終了する方法と、マップの名前を変更する方法
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のマップは、.btm という拡張子付きのファイルとして、ファイル システム内に格納されます。 ただし、マップを開く、保存する、閉じるなどの操作は、BizTalk プロジェクト内から行うのが一般的です。  
  
### <a name="to-open-a-map"></a>マップを開くには  
  
1.  ソリューション エクスプローラーで、開くマップを選択します。  
  
2.  **ビュー**  メニューのをクリックして**開く**です。  
  
     マップは、BizTalk マッパーで開きます。  
  
    > [!NOTE]
    >  ソリューション エクスプ ローラーでマップを右クリックしてをクリックして**開く**、またはソリューション エクスプ ローラーでマップをダブルクリックします。  
  
### <a name="to-save-a-map"></a>マップを保存するには  
  
1.  ソリューション エクスプローラーで、保存するマップを選択します。  
  
2.  **ファイル** メニューのをクリックして**保存*\<名のマップの\>***です。  
  
### <a name="to-save-a-map-to-a-new-location"></a>マップを別の場所に保存するには  
  
1.  ソリューション エクスプローラーで、マップの保存先を選択します。  
  
2.  **ファイル** メニューのをクリックして**保存*\<名のマップの\>*として**です。  
  
3.  **ファイルに名前を付けて** ダイアログ ボックスで、マップを保存するフォルダーの場所を参照します。  
  
4.  **ファイル名**ボックスで、ファイルの名前を入力し、をクリックして**保存**です。  
  
    > [!IMPORTANT]
    >  マップに次の名前を使用しないでください。"XmlContent"、"SourceSchemas"、"TargetSchemas"、または"XsltArgumentListContent"です。そのためコンパイルで問題が発生、対応する .NET アセンブリで生成された c# コードです。 問題とその解決方法については、次を参照してください。[マップのトラブルシューティング](../core/troubleshooting-maps.md)です。  
  
### <a name="to-rename-a-map"></a>マップの名前を変更するには  
  
1.  ソリューション エクスプ ローラーで、名前を変更し、をクリックする地図を右クリックして**の名前を変更**です。  
  
2.  ソリューション エクスプローラーで、マップ位置に表示された編集ボックスに新しいマップ名を入力するか、既存の名前を変更し、Enter キーを押します。  
  
> [!NOTE]
>  変更することも、**型名**の名前を変更するときにマップします。 変更する、**型名**を選択して、**マップ**、ソリューション エクスプ ローラーと新しい名前を入力、**型名**プロパティ ウィンドウでします。  
  
#### <a name="to-close-a-map"></a>マップを閉じるには  
  
1.  ソリューション エクスプローラーで、閉じるマップを選択します。  
  
2.  **[ファイル]** メニューの **[閉じる]**をクリックします。  
  
    > [!NOTE]
    >  閉じるアイコンをクリックすることもできます (**[x]**)、Microsoft の右上隅に[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のマップの管理](../core/managing-maps-within-projects.md)