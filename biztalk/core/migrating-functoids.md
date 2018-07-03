---
title: Functoid の移行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b01f37551b9d4c1aef13786be7094504f8cee08
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020504"
---
# <a name="migrating-functoids"></a>Functoid の移行
BizTalk Server の以前のバージョンから BizTalk Server にマップを移行する場合、マップに含まれる functoid も移行されます。 移行する functoid が含まれない場合**Scripting** functoid の場合、追加の移行タスクは必要ありません。 ただし、マップが含まれている場合**Scripting** functoid またはカスタム functoid では、追加の手順を実行する必要があります。  
  
 BizTalk Server の以前のバージョンに含まれるすべてのカスタム スクリプトを**Scripting** functoid はインラインで書き込まれました。 つまり、Functoid を作成する際、実行時に Functoid で呼び出されるすべてのスクリプトが Functoid と共に格納されていました。 別の functoid で同じスクリプトを使用する場合をコピーして貼り付けるか、いずれかから**Scripting**にするか、別の functoid がゼロからスクリプトを書き直しています。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、マップを移行すると、Functoid と共に既存のインライン スクリプトもコピーされます。 ただし、すべてのスクリプトが正しく機能します。 BizTalk Server は、VBScript ではなく、Visual Basic .NET および JScript .NET を使用し、JScript が以前のバージョンで使用します。 .NET バージョンの言語では、構文に一部の変更があります。  
  
> [!NOTE]
>  必ずテストして、 **Scripting** functoid は移行後にします。  
  
 カスタム functoid を書き直す必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] .NET framework を使用するカスタム functoid が必要です。 COM ベースの古いカスタム Functoid は使用できません。 .NET Framework を使用するように、カスタム Functoid を作成し直してください。 カスタム functoid のサンプル コードを参照してください。[カスタム Functoid (BizTalk Server サンプル)](../core/custom-functoid-biztalk-server-sample.md)します。  
  
 代わりに、外部アセンブリにカスタム functoid の機能をラップし、使用してこのアセンブリを呼び出すし、 **Scripting** functoid。 次のセクションでは、この方法について説明します。  
  
### <a name="to-migrate-your-custom-functoids"></a>カスタム Functoid を移行するには  
  
1. Functoid の機能を、Microsoft Visual Basic .NET、JScript .NET、Microsoft Visual C# .NET などの .NET 言語で再作成します。  
  
2. 新しい機能を含むアセンブリを作成します。  
  
3. グローバル アセンブリ キャッシュ (GAC) にアセンブリを登録します。  
  
   > [!NOTE]
   >  グローバル アセンブリ キャッシュにアセンブリを登録するには、アセンブリに厳密な名前を付けて署名する必要があります。 アセンブリ登録の詳細については、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 連結ヘルプ コレクションの「グローバル アセンブリ キャッシュ」を参照してください。  
  
4. 含むマップとの間の参照を作成、 **Scripting** functoid と再作成された機能を格納するアセンブリ。  
  
5. 構成、**スクリプト**プロパティを**Scripting** functoid。 このプロパティは、どのようなスクリプトを決定します、 **Scripting**実行時に functoid の呼び出し。 このプロパティの値と、カスタム スクリプトの再作成で使用した言語を一致させる必要があります。 スクリプト プロパティを構成する方法の詳細については、次を参照してください。 [Functoid のプロパティを編集および入力パラメーター](../core/editing-functoid-properties-and-input-parameters.md)します。 参照してください[スクリプト Functoid の](../core/scripting-functoid.md)します。  
  
6. マップを含んでいる BizTalk プロジェクトをビルド、 **Scripting** functoid。  
  
7. マップの検証とテストを行います。  
  
## <a name="see-also"></a>参照  
 [Functoid のプロパティおよび入力パラメーターの編集](../core/editing-functoid-properties-and-input-parameters.md)   
 [スクリプト Functoid](../core/scripting-functoid.md)