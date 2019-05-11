---
title: ポリシーのバージョンを管理する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, publishing
- publishing policies
- updating, policies
- versioning, policies
- policies, versioning
- policies, updating
ms.assetid: 6e35b2bd-1ecd-45ea-aff3-4ad2437568a4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78750e9db681ad12b1a134ef27360a57a3163bc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336829"
---
# <a name="how-to-maintain-policy-versions"></a>ポリシーのバージョンを管理する方法
ポリシーのバージョンをルールを追加した後は、バージョンを保存するには、将来の開発をルール ストアにまたは明確に定義された、変更できない一連のルール ベースのアプリケーションで使用するためにデプロイできる規則の作成に発行することができます。  
  
 このトピックには、次のタスクの手順が含まれています。  
  
-   ポリシーの空の新しいバージョンを作成するには  
  
-   ポリシー バージョンを保存するには  
  
-   ポリシー バージョンを発行するには  
  
-   ポリシーの更新バージョンを作成するには  
  
-   更新されたアセンブリを使用するポリシーを更新するには  
  
### <a name="to-create-an-empty-new-version-of-a-policy"></a>ポリシーの空の新しいバージョンを作成するには  
  
-   ポリシー フォルダーを右クリックし、**新しいバージョンの追加**します。  
  
### <a name="to-save-a-policy-version"></a>ポリシー バージョンを保存するには  
  
-   ポリシーのバージョンを右クリックし、をクリックし、**保存**します。  
  
### <a name="to-publish-a-policy-version"></a>ポリシー バージョンを発行するには  
  
-   ポリシーのバージョンを右クリックし、をクリックし、**発行**します。  
  
### <a name="to-create-an-updated-version-of-a-policy"></a>ポリシーの更新バージョンを作成するには  
  
1.  既存のポリシーのバージョンを右クリックし、をクリックし、**コピー**します。  
  
2.  ポリシー フォルダーを右クリックし、**貼り付け**します。  
  
     コピーされるバージョンと同じ要素を新しいバージョンが作成されます。  
  
    > [!NOTE]
    >  ポリシーは、.NET アセンブリを使用して、アセンブリが更新された場合は、アセンブリの新しいバージョンに、ポリシーをバインドする必要があります。  
  
### <a name="to-update-a-policy-to-use-an-updated-assembly"></a>更新されたアセンブリを使用するポリシーを更新するには  
  
1.  をクリックして**開始**、 をポイント**管理ツール**、 をポイント **.NET Framework 構成**、順にクリックします**構成アセンブリ**.  
  
2.  ターゲット アセンブリのプロパティに移動し、**バインド ポリシー**タブ。  
  
3.  グローバル アセンブリ キャッシュより新しいバージョンに、バージョン番号を変更します。  
  
    > [!NOTE]
    >  ポリシーによって使用されるすべてのアセンブリは、グローバル アセンブリ キャッシュに追加する必要があります。