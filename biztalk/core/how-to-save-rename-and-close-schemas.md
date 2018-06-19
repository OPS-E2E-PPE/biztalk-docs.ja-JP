---
title: 保存、名前変更、およびスキーマを閉じる方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65e15d9e-40ae-4850-9c13-88033cb3b3bb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a295bacf263e3ecad9a9aa081fb0d5d3be2f635
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "25972368"
---
# <a name="how-to-save-rename-and-close-schemas"></a>スキーマの保存、名前変更、および終了の方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、スキーマは XSD (XML Schema Definition) 言語ファイルであり、ファイル システムに .xsd という拡張子で格納されます。 BizTalk エディターを使用したスキーマの作成には、スキーマ ファイルの保存と終了、場合によっては、ファイル名の変更といった作業が常に伴います。 このトピックでは、こうした基本操作に必要な手順について説明します。  
  
### <a name="to-save-a-schema"></a>スキーマを保存するには  
  
1.  必要に応じて、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウ上部にある適切なタブをクリックして、保存するスキーマの BizTalk エディターをアクティブにします。  
  
2.  **ファイル** メニューのをクリックして * * 保存 *\<名前のスキーマ\>* * *。  
  
     スキーマに対する変更がまだ保存されていなかった場合、スキーマを保存すると、メイン編集ウィンドウ上部のタブに表示される名前からアスタリスク (*) が消えます。このアスタリスクは、変更内容が保存されていないことを示すマークです。  
  
> [!NOTE]
>  クリックして、新しい名前でスキーマを保存することができます**保存*\<名前のスキーマ\>* として**上、**ファイル**メニュー。  
  
> [!NOTE]
>  クリックして、プロジェクトの変更されたすべての項目の保存の一部としてスキーマを保存する **すべてを保存** 上、 **ファイル** メニュー。  
  
#### <a name="to-rename-a-schema"></a>スキーマ名を変更するには  
  
1.  ソリューション エクスプ ローラーでクリックして、名前を変更するスキーマを右クリックし **の名前を変更**します。  
  
2.  ソリューション エクスプローラーで、スキーマの位置に表示された編集ボックスに新しいスキーマ名を入力するか、既存の名前を変更し、Enter キーを押します。  
  
> [!NOTE]
>  変更することも、 **型名** の名前を変更するときのスキーマです。 変更する、 **型名** を選択して、 **スキーマ** に新しい名前を入力し、ソリューション エクスプ ローラーで、 **型名** プロパティ ウィンドウでします。  
  
> [!IMPORTANT]
>  他のスキーマで使われているスキーマの名前を変更することはできません。 たとえば、他のスキーマによってインクルード、インポート、または再定義されたスキーマや、既に昇格が設定されたプロパティ スキーマなどです。 これらのスキーマの名前を変更した場合、使用されているスキーマが、名前の変更されたスキーマを見つけることができなくなります。  
  
> [!NOTE]
>  プロジェクトのメンバー ファイル (スキーマ ファイルなど) に特定の名前を使用すると、C# の予約語や NET Framework の型/名前空間名 ("System" など) との競合によってコンパイル エラーになる場合があります。 このようなスキーマ名には、schema.xsd、XmlContent、RootNodes などがあります。 これは、 **型名** の基本 (拡張子を除いた部分のプロパティの既定値、 **Filename** プロパティです。 この種のコンパイル エラーを回避するには、明示的の値を変更して、 **型名** 競合しないやすいプロパティです。  
  
#### <a name="to-close-a-schema"></a>スキーマを終了するには  
  
1.  必要に応じて、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] のメイン編集ウィンドウ上部にある適切なタブをクリックして、終了するスキーマの BizTalk エディターをアクティブにします。  
  
2.  **[ファイル]** メニューの **[閉じる]** をクリックします。  
  
     BizTalk エディターによってスキーマが終了されます。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のスキーマの管理](../core/managing-schemas-within-projects.md)