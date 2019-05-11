---
title: 保存、名前の変更、およびスキーマを終了する方法 |Microsoft Docs
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
ms.openlocfilehash: 13944689885ea504679591fcaabb2f442c486de1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334845"
---
# <a name="how-to-save-rename-and-close-schemas"></a>保存、名前の変更、およびスキーマを終了する方法
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマの XML スキーマ定義 (XSD) 言語ファイルをおよび .xsd の拡張子を持つファイル システム上に存在します。 BizTalk エディターを使用してスキーマを開発してスキーマ ファイルを閉じて保存する必要があります定期的に場合によっては、それらの名前を変更する必要があります。 このトピックでは、これらの基本操作の実行に必要な手順について説明します。  
  
### <a name="to-save-a-schema"></a>スキーマを保存するには  
  
1. 必要に応じて、Microsoft では、メイン編集ウィンドウの上部にある適切なタブをクリックして、保存するスキーマの BizTalk エディターをアクティブ化[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
2. **ファイル** メニューのをクリックして * * 保存 *\<名前のスキーマ\>* * *。  
  
    場合は、スキーマには、変更が保存されていませんが、メイン編集ウィンドウの上部にあるタブに表示される名前は不要になった 未保存の変更を示すために使用されるアスタリスク (*) で終了します。  
  
> [!NOTE]
>  クリックして、新しい名前でスキーマを保存する**保存*\<スキーマの名前\>* として**上、**ファイル**メニュー。  
  
> [!NOTE]
>  スキーマを保存するには、プロジェクト内をクリックして変更されたすべての項目の保存の一部として**すべてを保存**上、**ファイル**メニュー。  
  
#### <a name="to-rename-a-schema"></a>スキーマの名前を変更するには  
  
1.  ソリューション エクスプ ローラーで、クリックして、名前を変更するスキーマを右クリックして**の名前を変更**します。  
  
2.  ソリューション エクスプ ローラーでスキーマの場所に表示される編集ボックスで、スキーマの新しい名前を入力や、既存の名前を変更し、ENTER キーを押します。  
  
> [!NOTE]
>  変更することも、**型名**の名前を変更するときにスキーマ。 変更する、**型名**を選択して、**スキーマ**ソリューション エクスプ ローラーと新しい名前を入力、**型名**プロパティ ウィンドウでします。  
  
> [!IMPORTANT]
>  別のスキーマで使用されている任意のスキーマの名前を変更する必要がありますされません。 これには、スキーマに含まれる、インポート、または再定義されているプロモーションが確立されて既にプロパティ スキーマおよびその他のスキーマによってが含まれます。 これを行う場合、使用されているスキーマが含まれている名前に正確なされなくなるために、変更されたスキーマを検索できません。  
  
> [!NOTE]
>  特定の名前のスキーマ ファイルなどのプロジェクト メンバー ファイルなる競合によってコンパイル エラー c# 予約語で ("System") などと.net Framework 型と名前空間名。 スキーマの例には、schema.xsd、XmlContent、および Rootnode が含まれます。 これは、ため、**型名**プロパティの既定値の基本 (拡張機能) の部分、**ファイル名**プロパティ。 この種のコンパイル エラーを回避するには、値を明示的に変更することで、**型名**プロパティを競合しないようにします。  
  
#### <a name="to-close-a-schema"></a>スキーマを閉じる  
  
1. 必要に応じて、Microsoft では、メイン編集ウィンドウの上部にある適切なタブをクリックして、終了するスキーマの BizTalk エディターをアクティブ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
2. **[ファイル]** メニューの **[閉じる]** をクリックします。  
  
    閉じられているスキーマの BizTalk エディターを閉じます。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のスキーマの管理](../core/managing-schemas-within-projects.md)