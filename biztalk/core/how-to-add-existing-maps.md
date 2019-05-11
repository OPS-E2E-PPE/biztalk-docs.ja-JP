---
title: 既存のマップを追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbeaea05-016e-488c-90f3-af8c6b9a3d84
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a566a76d1d42d099e1825af7d6774644bb9049d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387298"
---
# <a name="how-to-add-existing-maps"></a>既存のマップを追加する方法
既存のマップを BizTalk プロジェクトに追加する場合があります。 これを行うには、前に、マップの元と送信先スキーマがマップを追加する BizTalk プロジェクトに含まれることを確認する必要があります。または、対応する .NET アセンブリによって参照されています。  
  
### <a name="to-add-an-existing-map-to-a-biztalk-project"></a>既存のマップを BizTalk プロジェクトに追加するには  
  
1. ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。  
  
2. **既存項目の追加** ダイアログ ボックスで、追加で選択しをクリックするマップを含むフォルダーを参照し**追加**します。  
  
    マップは、BizTalk マッパーで開きます。 新しく追加したマップは、ソリューション エクスプ ローラーで現在の BizTalk プロジェクトの子としても表示されます。  
  
   > [!NOTE]
   >  BizTalk プロジェクト フォルダー以外のフォルダーを参照した場合、プロジェクト フォルダーに追加したマップのコピーが作成されたし、このプロジェクトに追加されたマップのコピーがします。 その後、マップに変更は、他のフォルダー内の元のマップが、このコピーされます。  
   > 
   > [!IMPORTANT]
   >  BizTalk マップは、Microsoft 内でホストされている BizTalk マッパーによってのみ開くこと[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]シェルです。 Windows エクスプ ローラーの新しいインスタンスのマップをダブルクリック[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、開く、マップが BizTalk マッパーで表示されます、対応するスキーマが正しく読み込まれています。  
   > 
   > [!NOTE]
   >  既存のマップにカスタム functoid が含まれている場合、"%BTSINSTALLPATH%\Developer tools \mapper Extensions"フォルダーに対応する Dll をコピーする必要があります。 それ以外の場合、マップは読み込まれず、カスタム functoid の読み込みに失敗したため、エラーをスローします。  
  
## <a name="see-also"></a>参照  
 [プロジェクト内のマップを管理します。](../core/managing-maps-within-projects.md)   
 [カスタム Functoid の開発](../core/developing-custom-functoids.md)