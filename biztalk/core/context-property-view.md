---
title: コンテキスト プロパティ ビュー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, message schemas
- Context Property view [Tracking Profile Editor]
- Tracking Profile Editor, Context Property view
- message schemas, XML messages
ms.assetid: 17a21b86-995c-4dc2-9a3c-1309837d0b9b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84a0f3a1d507e1440f67cd5f9e4afa18bff0b52a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237882"
---
# <a name="context-property-view"></a>コンテキスト プロパティ ビュー
コンテキスト プロパティ ビューには、プロパティと関連付けられている XML メッセージのスキーマが表示されます。 このビューは、オーケストレーション スケジュール ビューにある一部の図形のショートカット メニューから使用できます。  
  
## <a name="working-with-the-context-property-view"></a>コンテキスト プロパティ ビューの操作  
 クリックして、コンテキスト プロパティ ビューを選択する、**イベント ソースの選択**ボタンをクリックしをクリックすると、 **コンテキスト プロパティの**メニュー項目。 次に、既知のコンテキスト プロパティの一覧からコンテキスト プロパティを選択し、そのプロパティのスキーマを読み込みます。 プロパティを選択すると、関連付けられたスキーマからアクティビティのデータ項目フォルダーに要素をドラッグできます。つまり、このアクションのメッセージ内の特定の XPath 式からデータを抽出できます。  
  
 コンテキスト プロパティを含む図形を右クリックすると、オーケストレーション スケジュール ビューからコンテキスト プロパティ ビューを開くことができます。 クリックしてコンテキスト メニューが開き、この、**コンテキスト プロパティ スキーマ**図形に関連付けられているコンテキスト プロパティの一覧を取得するメニュー項目。  
  
 このコンテキスト プロパティの一覧には、使用可能なプロパティが非常に多く表示される場合があります。 検索対象のプロパティの名前の一部がわかっている場合でを入力、**文字列**テキスト ボックスをクリック、**検索**ボタンをクリックします。 これにより、入力した文字列を含むプロパティのみが選択され、表示されます。  
  
> [!NOTE]
>  コンテキスト プロパティ ビューからマップする場合、プロパティ スキーマの一覧には、BizTalk Server で構成されているすべてのプロパティ スキーマが含まれます。  一覧に表示されたスキーマは、操作している BizTalk Server のプロセスで使用されている機能とは対応していません。 たとえば、実行中のプロセスで SOAP が使用されていなくても、コンテキスト プロパティからマップすると、スキーマの一覧から SOAP プロパティのスキーマを選択することができます。 未使用のプロパティからマップされた BAM アクティビティ項目は、BAM では NULL または空のデータとしてキャプチャされます。  
  
## <a name="see-also"></a>参照  
 [イベント ソース ビューとは何ですか。](../core/what-is-the-source-event-view.md)   
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)