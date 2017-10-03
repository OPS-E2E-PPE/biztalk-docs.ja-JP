---
title: "Functoid の移行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functoids, migrating
- migrating, maps
- Migrating functoids, about Migrating functoids
- Migrating functoids
- Scripting functoids
- migrating, functoids
- migrating, Scripting functoids
ms.assetid: fc5b3ac9-28c6-41df-b779-15a8c3188528
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72f9769a571eb9b04cee21e42f5e75afbbadfafa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="migrating-functoids"></a>Functoid の移行
以前のバージョンの BizTalk Server から [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] にマップを移行すると、マップに含まれる Functoid も移行されます。 移行する functoid が含まれない場合**スクリプト**functoid、追加の移行タスクは必要ありません。 ただし、マップが含まれる場合**スクリプト**functoid またはカスタム functoid を追加の手順を実行する必要があります。  
  
 すべてのカスタム スクリプトを BizTalk Server の以前のバージョンに含まれている、**スクリプト**functoid がインラインで書き込まれました。 つまり、Functoid を作成する際、実行時に Functoid で呼び出されるすべてのスクリプトが Functoid と共に格納されていました。 別の functoid で同じスクリプトを使用する場合をコピーして貼り付けるか、いずれかから**スクリプト**するか、別の functoid を最初からスクリプトを書き直していました。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、マップを移行すると、Functoid と共に既存のインライン スクリプトもコピーされます。 ただし、すべてのスクリプトは正常に機能します。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Visual Basic .NET および JScript .NET ではなく VBScript と JScript の以前のバージョンを使用します。 .NET バージョンの言語では、構文に一部の変更があります。  
  
> [!NOTE]
>  必ずテストして、**スクリプト**functoid を移行した後です。  
  
 カスタム functoid を書き直す必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].NET framework を使用するカスタム functoid が必要です。 COM ベースの古いカスタム Functoid は使用できません。 .NET Framework を使用するように、カスタム Functoid を作成し直してください。 カスタム functoid のサンプル コードは、次を参照してください。[カスタム Functoid (BizTalk Server サンプル)](../core/custom-functoid-biztalk-server-sample.md)です。  
  
 外部アセンブリにカスタム functoid の機能をラップして、によってこのアセンブリを呼び出すには、代わりに、**スクリプト**functoid です。 次のセクションでは、この方法について説明します。  
  
### <a name="to-migrate-your-custom-functoids"></a>カスタム Functoid を移行するには  
  
1.  Functoid の機能を、Microsoft Visual Basic .NET、JScript .NET、Microsoft Visual C# .NET などの .NET 言語で再作成します。  
  
2.  新しい機能を含むアセンブリを作成します。  
  
3.  グローバル アセンブリ キャッシュ (GAC) にアセンブリを登録します。  
  
    > [!NOTE]
    >  グローバル アセンブリ キャッシュにアセンブリを登録するには、アセンブリに厳密な名前を付けて署名する必要があります。 アセンブリ登録の詳細については、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 連結ヘルプ コレクションの「グローバル アセンブリ キャッシュ」を参照してください。  
  
4.  含むマップとの間の参照を作成、**スクリプト**functoid とを再作成された機能を含むアセンブリです。  
  
5.  構成、**スクリプト**プロパティを**スクリプト**functoid です。 このプロパティは、どのようなスクリプトを決定、**スクリプト**functoid の呼び出し時に実行します。 このプロパティの値と、カスタム スクリプトの再作成で使用した言語を一致させる必要があります。 スクリプト プロパティを構成する方法の詳細については、次を参照してください。 [Functoid のプロパティを編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)です。 参照してください[スクリプト Functoid の](../core/scripting-functoid.md)します。  
  
6.  マップを含んでいる BizTalk プロジェクトをビルド、**スクリプト**functoid です。  
  
7.  マップの検証とテストを行います。  
  
## <a name="see-also"></a>参照  
 [Functoid のプロパティおよび入力パラメーターの編集](../core/editing-functoid-properties-and-input-parameters.md)   
 [スクリプト Functoid](../core/scripting-functoid.md)