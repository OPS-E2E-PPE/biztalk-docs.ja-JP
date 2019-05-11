---
title: Namespace コンポーネントのテストを実行している |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13768608-ade6-44c0-897f-d417c3408302
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e60a4ee44d80747bdeb50ac199c2d5354482abb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242705"
---
# <a name="running-the-namespace-component-tests"></a>Namespace コンポーネントのテストを実行しています。
次の手順は 4 つのテスト シナリオのすべてを実行する方法を示しています、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Namespace コンポーネント サンプル。  
  
 **Namespace コンポーネント サンプルのテスト シナリオを実行するには**  
  
1.  最初にこのサンプルを実行する前に、受信場所と送信ポートの URL を指しているソース配布ファイルの適切なサブフォルダーを確認します。 受信場所のサブフォルダー \Source\Samples\Namespace\Test\Filedrop\In と送信ポートの URL のサブフォルダー \Source\Samples\Namespace\Test\Filedrop\Out を指定します。  
  
2.  GlobalBank.ESB アプリケーションが実行されていない場合は、Microsoft の BizTalk 管理コンソールを使用して、開始します。  
  
3.  (、ESB のインストール フォルダーの \Source\Samples\Namespace\Test\Data\ サブフォルダーにあります)、TEST_Add_to_PassThrough.0000.ns.xml という名前のファイルのコピーを作成し、「test _」プレフィックスを削除することで、コピーの名前を変更します。  
  
4.  \Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。  
  
5.  ESB メッセージを取得するには、名前空間を追加および \Source\Samples\Namespace\Test\Filedrop\Out サブフォルダーに更新されたメッセージをドロップします。 入力を開き、このテストの効果を表示するテキスト エディターでファイルを出力します。  
  
6.  2 つ目のテストを実行します。 TEST_Add_to_Remove.0000.ns.xml という名前のファイルのコピーを作成し、「test _」プレフィックスを削除して名前を変更します。  
  
7.  \Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。  
  
8.  ESB でメッセージを取得、名前空間を追加、新しい名前空間を削除しますおよび \Source\Samples\Namespace\Test\Filedrop\Out サブフォルダーに更新されたメッセージをドロップします。 入力を開き、このテストの効果を表示するテキスト エディターでファイルを出力します。  
  
9. 3 番目のテストを実行します。 TEST_PassThrough_to_Remove.0000.ns.xml という名前のファイルのコピーを作成し、「test _」プレフィックスを削除して名前を変更します。  
  
10. \Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。  
  
11. ESB メッセージを取得するには、既存の名前空間を削除および \Source\Samples\Namespace\Test\Filedrop\Out サブフォルダーに更新されたメッセージをドロップします。 入力を開き、このテストの効果を表示するテキスト エディターでファイルを出力します。  
  
12. 最後に、4 番目のテストを実行します。 TEST_AddViaExtraction_to_PassThrough.0000.ns.xml という名前のファイルのコピーを作成し、「test _」プレフィックスを削除して名前を変更します。  
  
13. \Source\Samples\Namespace\Test\Filedrop\In サブフォルダーに名前が変更されたファイルをコピーします。  
  
14. ESB は、メッセージを取得で指定された要素を抽出し、 **ExtractionNodeXPath**プロパティ、この要素で指定された名前空間の値からメッセージを作成し、\Source\Samples\ に更新されたメッセージをドロップします。Namespace\Test\Filedrop\Out サブフォルダーです。 入力を開き、このテストの効果を表示するテキスト エディターでファイルを出力します。