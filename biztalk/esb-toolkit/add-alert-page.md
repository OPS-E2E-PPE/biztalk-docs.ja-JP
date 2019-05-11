---
title: アラートの追加ページ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0023ee8d-a0d1-4257-95c6-38c95060bd62
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c60c0b495a4d472ea45f9622e61b6a6deb9d95dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400143"
---
# <a name="add-alert-page"></a>アラートの追加ページ
図 1 は、ポータルに、アラートに指定した条件 (条件) に一致するエラー メッセージが到着すると、ポータルが表示される新しいアラートを作成する、アラートの追加 ページを示します。  
  
 ![アラートの追加ページ](../esb-toolkit/media/ch8-addalertpage.gif "Ch8 AddAlertPage")  
  
 **図 1**  
  
 **ESB 管理ポータル アラートの追加ページ**  
  
 アラートの追加 ページには、次の操作を行うことができます。  
  
-   新しいアラートの名前を入力、**アラート名の入力**テキスト ボックス。  
  
-   アラートが受信の例外のフィールドの値を照合する方法を指定、**このアラートの条件を追加**このページのセクション。 例外のスキーマからフィールドを選択します (など**アプリケーション、エラーの種類、** または**エラーの重大度)** で、**条件**ドロップダウン リストは、(このような比較の種類の選択=、 **! =、> =、< =、** または**など**) で、**演算子**ドロップダウン リストと型、または 3 番目のリストから値を選択します。 例外フィールドを選択すると、**値**テキスト ボックスまたは入力するか、一致する値を選択するためのドロップダウン リストのいずれかの変更を制御します。  
  
-   選択するか、条件値を入力する、クリックして、**追加**リンクの一覧にこの条件を追加する、**条件**セクションのページ、および繰り返し、さらにこのアラートに必要な条件を追加するには.  
  
-   をクリックして、**保存**指定した条件と名前で新しいアラートを作成するボタンをクリックします。