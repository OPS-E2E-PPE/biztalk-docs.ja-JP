---
title: 開く、保存、終了、およびマップの名前を変更する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9aa88ca7-a731-4295-8692-6dd36fdf0872
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a95ba8e22baa10a0b47721b8a8b3eb3554e2b8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968763"
---
# <a name="how-to-open-save-close-and-rename-maps"></a>マップを開く、保存、終了する方法と、マップの名前を変更する方法
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のマップは、.btm という拡張子付きのファイルとして、ファイル システム内に格納されます。 ただし、マップを開く、保存する、閉じるなどの操作は、BizTalk プロジェクト内から行うのが一般的です。  
  
### <a name="to-open-a-map"></a>マップを開くには  
  
1.  ソリューション エクスプローラーで、開くマップを選択します。  
  
2.  **ビュー**  メニューのをクリックして**オープン**します。  
  
     マップは、BizTalk マッパーで開きます。  
  
    > [!NOTE]
    >  ソリューション エクスプ ローラーでマップを右クリックしてもをクリックしたことができます**オープン**、またはソリューション エクスプ ローラーでマップをダブルクリックします。  
  
### <a name="to-save-a-map"></a>マップを保存するには  
  
1. ソリューション エクスプローラーで、保存するマップを選択します。  
  
2. **ファイル** メニューのをクリックして * * 保存 *\<名のマップの\>* * *。  
  
### <a name="to-save-a-map-to-a-new-location"></a>マップを別の場所に保存するには  
  
1.  ソリューション エクスプローラーで、マップの保存先を選択します。  
  
2.  **ファイル** メニューのをクリックして**保存*\<名のマップの\>* として**します。  
  
3.  **ファイルに名前を付けて** ダイアログ ボックスで、マップを保存するフォルダーの場所を参照します。  
  
4.  **ファイル名**ボックスで、ファイルの名前を入力し、クリックして**保存**します。  
  
    > [!IMPORTANT]
    >  マップに次の名前を使用しないでください"XmlContent"、"SourceSchemas"、"TargetSchemas"、"XsltArgumentListContent"または。そのためのコンパイルで問題が発生、対応する .NET アセンブリで生成された c# コード。 問題とその解決方法については、[マップのトラブルシューティング](../core/troubleshooting-maps.md)を参照してください。  
  
### <a name="to-rename-a-map"></a>マップの名前を変更するには  
  
1.  ソリューション エクスプ ローラーで、クリックして、名前を変更するマップを右クリックして**の名前を変更**します。  
  
2.  ソリューション エクスプローラーで、マップ位置に表示された編集ボックスに新しいマップ名を入力するか、既存の名前を変更し、Enter キーを押します。  
  
> [!NOTE]
>  変更することも、**型名**の名前を変更するときにマップします。 変更する、**型名**を選択して、**マップ**ソリューション エクスプ ローラーと新しい名前を入力、**型名**プロパティ ウィンドウでします。  
  
#### <a name="to-close-a-map"></a>マップを閉じるには  
  
1. ソリューション エクスプローラーで、閉じるマップを選択します。  
  
2. **[ファイル]** メニューの **[閉じる]** をクリックします。  
  
   > [!NOTE]
   >  ある閉じるアイコンをクリックすることもできます (**[x]**)、Microsoft の右上隅にある[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ウィンドウを編集します。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のマップの管理](../core/managing-maps-within-projects.md)