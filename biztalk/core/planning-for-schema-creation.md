---
title: スキーマの作成の計画 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ecb9154-b457-4209-b9b9-572c186bf5e7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 60fc7a3cafb3f13a189383df70d4b9ea0bf98f54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264642"
---
# <a name="planning-for-schema-creation"></a>スキーマの作成の計画
スキーマは、メッセージのインスタンスがその定義に準拠しているかどうかを検証したり、異なる形式 (XML と非 XML) のインスタンス メッセージを相互に変換するための方法を定義したり、あるいは、特定の構造を持つ XML インスタンス メッセージを、それとは別の構造を持つ XML インスタンス メッセージに変換する方法を定義したりする場合に使用されます。 インスタンス メッセージの変換とインスタンス メッセージの変換の違いの詳細については、次を参照してください。[変換 vs です。翻訳](../core/data-transformation.md)です。  
  
 次の表は、BizTalk エディターのスキーマ作成計画で検討する必要がある項目を示しています。  
  
|計画段階の考慮事項|推奨|  
|-----------------------|--------------------|  
|どのようなスキーマを作成するか|Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で処理するビジネス ドキュメントの一覧を作成します。 この一覧には、注文書、請求書、出荷情報などが含まれます。 また、一覧には、複数の異なるビジネス ドキュメントが含まれる場合もあります。たとえば、ある取引先から受け取った注文書の形式が別の取引先から受け取った注文書の形式と異なる場合などです。|  
|送受信の対象となるドキュメントが既に XML 化されているか|送受信の対象となる各ビジネス ドキュメントの形式に関する情報 (既に XML 化されているのか、または、区切り文字/位置指定のフラット ファイル形式かなど) を、ドキュメントの一覧に追加します。|  
|スキーマの作成に利用できるソースはあるか|元になるソースがない場合、スキーマの作成には若干の手間がかかります。 スキーマが既に XSD (XML Schema Definition) 言語で表記されていれば、スキーマを生成する必要はありません。BizTalk エディターでそのまま開くことができます。<br /><br /> 整形式 XML のインスタンス メッセージ、ドキュメント型定義 (DTD)、XDR (XML-Data Reduced) のいずれかが存在する場合は、それを元にスキーマを自動的に生成できます。 生成されたスキーマを BizTalk エディターで調整しなければならない場合もありますが、難しい作業ではありません。 手順については、"XSD 以外のソースからスキーマを生成するには」の手順を参照してください[XML メッセージ用スキーマの作成](../core/how-to-create-schemas-for-xml-messages.md)です。<br /><br /> 上記のいずれのソースも利用できない場合、BizTalk エディターを使って新しいスキーマを作成し、その構造を定義する必要があります。|  
  
## <a name="see-also"></a>参照  
 [XML メッセージ用スキーマを作成する方法](../core/how-to-create-schemas-for-xml-messages.md)   
 [BizTalk エディターを使用してスキーマを作成します。](../core/creating-schemas-using-biztalk-editor.md)