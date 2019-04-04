---
title: Oracle E-business Suite 操作の検索 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2970ddd4-a534-4da4-9bd5-28bb9da4deca
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e861f23a13f6c3e7d5ac500de3b7750429a9cfd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977211"
---
# <a name="search-for-oracle-e-business-suite-operations"></a>Oracle E-business Suite 操作の検索
使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Oracle E-business Suite での特定の成果物を検索します。 さまざまなビューとその内容の検索がサポートされている方法を説明しています Oracle アイテムを検索するためのワイルドカード文字を使用できます。 このトピックを使用して検索する方法の情報を提供することも、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  


  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] 、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、両方のコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
 詳細については、[Oracle E-business Suite アダプターを使用して、SharePoint と](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)を参照してください。  
  
## <a name="prerequisites"></a>前提条件  
 対象の操作のメタデータを検索する前に、Oracle E-business Suite に接続する必要があります。 使用する時に、データベース、Oracle に接続する方法については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)します。  
  
## <a name="support-for-wildcard-characters"></a>ワイルドカード文字のサポート  
 Oracle E-business Suite のメタデータを使用して検索するときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]検索式でのワイルドカードとエスケープ文字をサポートしています。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|_ (アンダースコア)|1 文字と一致します。<br /><br /> たとえば、<curses.h は AB、AC、AD と一致します。|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、%a、AB ABC に一致します。|  
|\ (エスケープ)|% と _ の特別な意味でのエスケープします。<br /><br /> たとえば、A\\_B A_B に一致します。|  
  
> [!NOTE]
>  エスケープ文字は、ワイルドカードではなく、通常の文字として、ワイルドカードを解釈することを示すワイルドカード文字の前に挿入されている文字です。  
  
## <a name="searching-under-different-views"></a>さまざまなビューを検索しています  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]と[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]3 つのビューにデータを分類 — アプリケーション ベースのビュー、成果物ベースのビューとスキーマ ベースのビュー。 これら 3 つのビューの下の成果物を分類する理由の 1 つは、探している内容に基づいて検索を行うためです。 次の表では、これらのビューで検索できるとは異なる方法について説明します。  
  
|表示|検索する方法|  
|----------|-------------------|  
|**アプリケーション ベースのビュー**|このビューは、Oracle E-business Suite アプリケーション名を使用して分類されます。 どのアプリケーションが使用する成果物を含むことがわかっている場合は、このビューを使用する必要があります。<br /><br /> このビューを使用してユーザーは、Oracle のアプリケーションには慣れているし、はどのようなアプリケーションを使用するのに注意してください。 そのため、このビューの下で検索は即時のレベルでのみサポートされています。 たとえば場合、**アプリケーション ベースのビュー**ノードが選択されている場合、ユーザーは、Oracle E-business Suite でのアプリケーションを検索できます。 同様に場合、**インターフェイス テーブル**ノードが選択されている場合、ユーザーは、Oracle E-business アプリケーションで、インターフェイス テーブルを検索できます。|  
|**成果物ベースのビュー**|このビューは、Oracle E-business Suite の成果物によって分類されます。 Oracle E-business Suite のアプリケーションのアイテムを使用する場合、ユーザーはどの Oracle E-business Suite の成果物が使用するも、どのアプリケーションに属している成果物を認識している場合にこのビューを使用する必要があります。<br /><br /> このビューを使用して、ユーザー検索できます特定の成果物のすべての Oracle E-business Suite アプリケーション。 たとえば、ユーザーが選択できる、**インターフェイス テーブル**ノードと、文字列を使用して検索`AR%`します。 これは、検索を実行する方法です。<br /><br /> ため、インターフェイス テーブルは、さらに、アプリケーションの下に分類、AR 始めて、アプリケーションのすべてが表示されます。<br />-AR 以降すべてのインターフェイス テーブルが表示されます。 これらのテーブルは、任意の Oracle E-business suite アプリケーションに属することができます。<br /><br /> このビューを使用して Oracle データベース アイテムを使用する場合は、ユーザーが特定の成果物にログインする現在のスキーマまたはすべてのスキーマでいずれかを検索できます。 たとえば、ユーザーがプロシージャ CREATE_ACCOUNT が認識できないスキーマを使用する場合、プロシージャが属しているを選択すること、**すべてのスキーマ**ノードと、文字列を使用して検索`CREATE%`します。|  
|**スキーマ ベースのビュー**|このビューは、基になる Oracle データベースで使用できるスキーマによって分類されます。 スキーマが、成果物を使用することがわかっている場合は、このビューを使用する必要があります。<br /><br /> このビューを使用してユーザーを使用すると、成果物を持つスキーマに関する知識になります。 そのため、このビューの下で検索は即時のレベルでのみサポートされています。 たとえば場合、**ビューのスキーマに基づく**ノードが選択されている場合、ユーザーは、Oracle データベース内のスキーマを検索できます。 同様に場合、**テーブル**ノードが選択されている場合、ユーザーは、Oracle E-business アプリケーション内のテーブルを検索できます。|  
  
## <a name="searching-for-operations"></a>操作の検索  
 Oracle E-business Suite を使用してメタデータを検索する、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、次の手順に従います。  
  
#### <a name="to-search-metadata-in-oracle-e-business-suite"></a>Oracle E-business Suite でメタデータを検索するには  
  
1. Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2. **選択コントラクト型**一覧で、受信または送信の操作を検索するかどうかに基づく契約の種類を選択します。  
  
3. **カテゴリを選択**ボックスを検索する特定の成果物のカテゴリ ノードをクリックします。 たとえば、Oracle アプリケーションを検索するに次のようにクリックします。、**アプリケーション ベースのビュー**ノード。  
  
   > [!NOTE]
   >  アプリケーションを検索するには、フレンドリ名またはアプリケーションの短い名前を指定できます。 たとえば、検索するため、 **Receivables**検索文字列を指定するにはいずれかとしてアプリケーション`Receive%`または`AR`。 AR は、アプリケーションの短い名前です。  
  
4. **カテゴリで検索**ボックスに、特定の成果物を検索する検索式を入力します。 たとえば、"Customer"が、その名前の Oracle アプリケーションを検索するに次のように入力します。`%Customer%`します。  
  
   > [!NOTE]
   >  検索文字列が大文字小文字を区別します。  
  
5. 検索を開始するには、右矢印アイコンのボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件を満たすアイテムが一覧表示されます。  
  
    次の図には、名前に"Customer"が含まれている Oracle アプリケーション テーブルが表示されます。  
  
    ![Oracle E でメタデータを検索&#45;Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/e6278992-a475-4a35-8371-db862f25a720.gif "e6278992-a475-4a35-8371-db862f25a720")  
  
   > [!NOTE]
   >  同時実行プログラムを検索するには、フレンドリ名または同時実行プログラムの実際の名前を指定できます。 たとえば、検索するため、**顧客インターフェイス**同時実行プログラムのいずれかとして検索文字列を指定できます`%Customer Interface%`または`%RACUST%`します。 RACUST は、同時実行プログラムの実際の名前です。  
   >   
   >  また、検索結果は標準の同時実行プログラムの名前が指定した検索文字列と一致するかどうかに関係なく常に含まれます。  
  
## <a name="see-also"></a>参照  
 [参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)