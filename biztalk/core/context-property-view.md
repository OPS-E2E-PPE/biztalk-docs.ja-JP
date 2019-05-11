---
title: コンテキスト プロパティ ビュー |Microsoft Docs
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
ms.openlocfilehash: b622c9a82bb199b066dc75b77822a4f0c2e06bdb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390321"
---
# <a name="context-property-view"></a>コンテキスト プロパティ ビュー
コンテキスト プロパティ ビューには、プロパティに関連付けられた XML メッセージのスキーマが表示されます。 ビューは、一部の図形 オーケストレーション スケジュール ビューのショートカット メニューから利用できます。  
  
## <a name="working-with-the-context-property-view"></a>コンテキスト プロパティ ビューの操作  
 クリックして、コンテキスト プロパティ ビューを選択、**イベント ソースの選択**クリックし、 **コンテキスト プロパティの**メニュー項目。 コンテキスト プロパティは、そのプロパティのスキーマを読み込むの既知のコンテキスト プロパティの一覧から選択します。 プロパティを選択するとする要素をドラッグできます、関連付けられたスキーマからアクティビティのデータ項目フォルダーにこのアクションのメッセージ内の特定の XPath 式からそのデータを抽出することを示します。  
  
 オーケストレーション スケジュール ビューからコンテキスト プロパティ ビューを開くには、コンテキスト プロパティを含む図形を右クリックします。 クリックする、コンテキスト メニューが開きます、**コンテキスト プロパティ スキーマ**図形に関連付けられているコンテキスト プロパティの一覧を取得するメニュー項目。  
  
 使用可能なコンテキスト プロパティの一覧は広範にすることはできます。 検索対象のプロパティの名前の一部がわかっている場合でを入力、**文字列**テキスト ボックスをクリックして、**検索**ボタンをクリックします。 これにより、入力した部分文字列を含むプロパティのみが選択されます。  
  
> [!NOTE]
>  コンテキスト プロパティ ビューからマップを選択すると、潜在的なプロパティ スキーマの一覧は、BizTalk Server のインストールで構成されているすべてのプロパティ スキーマの完全な一覧を示します。  必要なスキーマの表示が機密性の高い、BizTalk Server の機能は、作業している実行中のプロセスによって使用されていないことに注意してください。 たとえば、マッピング、コンテキスト プロパティからすると、スキーマの一覧からの SOAP プロパティ スキーマを選択することができますが、実行中のプロセスは、SOAP を使用しない可能性があります。 BAM によってキャプチャされているデータを null または空で、未使用のプロパティの結果からマップされた BAM アクティビティ項目。  
  
## <a name="see-also"></a>参照  
 [イベント ソース ビューとは何ですか。](../core/what-is-the-source-event-view.md)   
 [追跡プロファイル エディター](../core/tracking-profile-editor.md)