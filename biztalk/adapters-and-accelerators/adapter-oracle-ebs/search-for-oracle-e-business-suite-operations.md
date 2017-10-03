---
title: "Oracle E-business Suite 操作の検索 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2970ddd4-a534-4da4-9bd5-28bb9da4deca
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 797f89b5032d6bcfdb1a4d16f5a83d53d01f1c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="search-for-oracle-e-business-suite-operations"></a>Oracle E-business Suite 操作の検索
使用することができます、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]Oracle E-business Suite での特定のアイテムを検索します。 このトピックのさまざまなビューとどのような検索をサポートする方法の情報を提供する Oracle アイテムを検索するため、ワイルドカード文字を使用できます。 このトピックの内容もについての情報を使用して検索する方法、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  


  
> [!NOTE]
>  [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]と[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]参照操作については、検索するため、両方のコンポーネントは、同じトピックで説明すると、基本的に同じインターフェイスを提供します。  
  
 詳細については、次を参照してください。[を SharePoint と、Oracle E-business Suite アダプターを使用して](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 次の操作を指定のメタデータを検索する前に、Oracle E-business Suite に接続する必要があります。 データベースを使用するときに、Oracle に接続する方法については、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)です。  
  
## <a name="support-for-wildcard-characters"></a>ワイルドカード文字のサポート  
 Oracle E-business Suite のメタデータを使用して検索するときに、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]検索式でのワイルドカードとエスケープ文字をサポートしています。  
  
|特殊文字|解釈|  
|-----------------------|--------------------|  
|_ (アンダースコア)|1 文字と一致します。<br /><br /> たとえば、a _ は、AB、AC、AD と一致します。|  
|% (割合)|0 個以上の文字と一致します。<br /><br /> たとえば、%a、AB、ABC に一致します。|  
|\ (エスケープ)|% と _ の特別な意味をエスケープします。<br /><br /> たとえば、A\\_B A_B に一致します。|  
  
> [!NOTE]
>  エスケープ文字は、通常の文字とは、ワイルドカードとしてではなくにワイルドカードを解釈することを示すためにワイルドカード文字の前に挿入されている文字です。  
  
## <a name="searching-under-different-views"></a>さまざまなビューを検索しています  
 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]と[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]3 つのビューにデータを分類-アプリケーション ベースのビュー、成果物に基づいたビュー、およびスキーマ ベースのビューです。 これら 3 つのビューの下の成果物を分類する理由の 1 つは、検索するに基づいて検索を行うためです。 次の表では、これらのビューで検索の違いについて説明します。  
  
|表示|検索する方法|  
|----------|-------------------|  
|**アプリケーション ベースのビュー**|このビューは、Oracle E-business Suite アプリケーション名を使用して分類されます。 どのアプリケーションが操作する成果物を含むことがわかっている場合に、このビューを使用する必要があります。<br /><br /> このビューを使用してユーザーは、Oracle アプリケーションには慣れているしは、使用するアプリケーションを認識します。 そのため、このビューの下にある検索は、イミディ エイトのレベルでのみサポートされてです。 たとえば場合、**アプリケーション ベースのビュー**ノードが選択されている場合、ユーザーは、Oracle E-business Suite でアプリケーションを検索できます。 同様に場合、**インターフェイス テーブル**ノードが選択されている場合、ユーザーは、Oracle E-business アプリケーション内のインターフェイス テーブルを検索できます。|  
|**成果物ベースのビュー**|このビューは、Oracle E-business Suite の成果物によって分類されます。 Oracle E-business Suite アプリケーション アイテムを使用する場合、ユーザーはどの Oracle E-business Suite の成果物を操作するこれらが不明な成果物が属するアプリケーションを認識している場合にこのビューを使用する必要があります。<br /><br /> このビューを使用して、ユーザーが検索できる、特定の成果物のすべての Oracle E-business Suite アプリケーションです。 たとえば、ユーザーが選択できる、**インターフェイス テーブル**ノードと、文字列を使用して検索`AR%`です。 検索を実行する方法を示します。<br /><br /> ため、インターフェイス テーブルは、[アプリケーション] で分類がさらに、AR でアプリケーションを起動すべてが表示されます。<br />-以降では、AR すべてのインターフェイス テーブルが表示されます。 これらのテーブルは、任意の Oracle E-business suite アプリケーションに属することができます。<br /><br /> このビューを使用して Oracle データベース アイテムを使用する場合は、ユーザーが、特定の成果物にログインする現在のスキーマまたはすべてのスキーマでいずれかを検索できます。 たとえば、ユーザーが認識できないはプロシージャ CREATE_ACCOUNT どのスキーマを使用する場合、プロシージャが属しているを選択すること、**すべてのスキーマ**ノードと、文字列を使用して、検索`CREATE%`です。|  
|**スキーマ ベースのビュー**|このビューは、基になる Oracle データベースで使用可能なスキーマで分類されます。 スキーマが使用するアイテムがわかっている場合に、このビューを使用する必要があります。<br /><br /> このビューを使用しているユーザーはそれらを操作する成果物を含んでいるスキーマを使い慣れてになります。 そのため、このビューの下にある検索は、イミディ エイトのレベルでのみサポートされてです。 たとえば場合、**ビューのスキーマに基づく**ノードが選択されている場合、ユーザーは、Oracle データベースでスキーマを検索できます。 同様に場合、**テーブル**ノードが選択されている場合、ユーザーは、Oracle E-business アプリケーション内のテーブルを検索できます。|  
  
## <a name="searching-for-operations"></a>操作の検索  
 Oracle E-business Suite を使用してメタデータを検索するには、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、次の手順を実行します。  
  
#### <a name="to-search-metadata-in-oracle-e-business-suite"></a>Oracle E-business Suite のメタデータを検索するには  
  
1.  Oracle E-business Suite への接続、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]または[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。 参照してください[Visual Studio での Oracle E-business Suite への接続](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md)手順についてはします。  
  
2.  **選択コントラクト型**一覧で、受信または送信操作を検索するかどうかに基づいてコントラクトの型を選択します。  
  
3.  **カテゴリを選択**ボックスで、対象を検索する特定の成果物のカテゴリ ノードをクリックします。 たとえば、Oracle アプリケーションの検索は、次のようにクリックします。、**アプリケーション ベースのビュー**ノード。  
  
    > [!NOTE]
    >  アプリケーションを検索するには、フレンドリ名またはアプリケーションの短い名前を指定できます。 たとえば、検索するため、**債権**アプリケーションのいずれかとして検索文字列を指定できます`Receive%`または`AR`です。 AR は、アプリケーションの短い名前です。  
  
4.  **カテゴリで検索**ボックスに、特定の成果物を検索する検索式を入力します。 たとえば、"Customer"が、名前、Oracle アプリケーションの検索は、次のように入力します。`%Customer%`です。  
  
    > [!NOTE]
    >  検索文字列では大文字小文字を区別します。  
  
5.  検索を開始するには、右矢印アイコンが付いたボタンをクリックします。 検索が完了した後、**利用可能なカテゴリと操作**ボックスに検索条件に適合するアイテムが一覧表示されます。  
  
     次の図では、その名前に"Customer"が含まれる Oracle アプリケーション テーブルが表示されます。  
  
     ![Oracle E &#45; でのメタデータの検索Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/e6278992-a475-4a35-8371-db862f25a720.gif "e6278992-a475-4a35-8371-db862f25a720")  
  
    > [!NOTE]
    >  同時実行プログラムを検索するには、フレンドリ名または同時実行プログラムの実際の名前を指定できます。 例については、検索する、**顧客インターフェイス**検索文字列を指定するにはいずれかとして同時実行プログラム`%Customer Interface%`または`%RACUST%`です。 RACUST は、同時実行プログラムの実際の名前です。  
    >   
    >  また、検索結果は、その名が指定した検索文字列と一致するかどうかに関係なく、標準的な同時実行プログラムを常に含まれます。  
  
## <a name="see-also"></a>参照  
 [参照、検索、および Oracle E-business Suite 操作のメタデータを取得](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)